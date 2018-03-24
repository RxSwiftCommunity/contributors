# Auto Deploys

Auto deploys describe setting up your CI so it automatically pushes a new Podspec to CocoaPods trunk on new releases. 
You can read more on the discussion and suggestion that lead to this here: [[Proposal] Resolve Deployment of new CocoaPods on a Community-level](https://github.com/RxSwiftCommunity/contributors/issues/44)

This tutorial will use Circle CI as an example, but should apply to Travis or any other CI that has a release step that lets you filter out tags. 

**Point person**: If you have any questions or you got stuck, feel free to ping @freak4pc in GitHub or Twitter; or otherwise, open an issue. 

## Obtaining a CocoaPods Trunk Token

A CocoaPods Trunk token is a token generated for a user registering a session with the `trunk` service. 
That token can be used by a server (such as a CI provider) as an authentication mechanism for commands such as `pod trunk push`, etc. 

### To obtain a token for your repository:

1. Make sure you've added `community@rxswift.org` as an owner of your CocoaPod, as defined in the [Contribution Guide](https://github.com/RxSwiftCommunity/contributors#checklist-for-transferring-ownership), e.g. using `pod trunk add-owner YourPodName community@rxswift.org`.

![Register a CocoaPods Owner](https://i.imgur.com/UnC4pgX.png)

2. If you aren't part of the `community@rxswift.org` email list, please [DM @freak4pc on Twitter](https://twitter.com/freak4pc) or [open an issue](https://github.com/RxSwiftCommunity/contributors/issues/new?title=Request%20for%20Communtiy%20Email%20Forwarding:%20[NAME]) asking to add your email to the list of emails `community@rxswift.org` forwards to.

3. Once you have proper email forwarding set up, register a session with trunk using the community e-mail, by using: `pod trunk register community@rxswift.org "RxSwift Community"`. You should receive an email to the `community@rxswift.org` address, asking you to confirm your session. Tap the link.

![Approved Session](https://i.imgur.com/BPvPGbS.png)

1. Once you have an approved & registered session, your next step would be getting the new CocoaPods trunk token generated for you. The token is location in your `~/.netrc` file. You can use the following command to automatically copy that token to your pasteboard:

```bash
awk '/trunk.cocoapods.org/{getline; getline; print $2}' ~/.netrc | pbcopy
```

2. Keep a copy of your session token somewhere safe (e.g. copy it to temporary file aside to not lose it for the next step)

3. Register a new session with your private email to overwrite the local community token. This is to ensure the token is only used by CI and not by your own computer. Use: `pod trunk register my@email.com "My Name"` and approve your session via the email link like before.

## Setting up your CI

Awesome job! You now have a valid token you can provide your CI so it can push CocoaPod Specs on your (or the community's) behalf. 

There are only two final steps left to this tutorial. 

1. In your CI Provider, set up a "Secure Environment Variable" named `COCOAPODS_TRUNK_TOKEN` with the token you acquired in the previous step. On Circle CI, this will look as follows:

![CircleCI Environment Variable](https://i.imgur.com/peWtCfP.png)

2. Add a release-level script that would trigger a `pod trunk push` for every new release tag you push up. On Circle CI v1, you'd add to your `circle.yml`: 

```yml
deployment:
  release:
    tag: /[0-9]+(\.[0-9]+)*/
    commands:
      - rm ~/.cocoapods/config.yaml # This hack is needed since CircleCI forces --verbose
      - pod trunk push --skip-tests --allow-warnings
```

This code will automatically push a new version of your Podspec whenever you create a new GitHub "Release" with a new tag attached to it.

**Note**: If your CI itself doesn't use CocoaPods for any of its build stages, and you get an error similar to `Unable to find a specification for SomeDependency depended upon by YourRepo`, you probably need to add a `pod setup` before your push, like here: https://github.com/RxSwiftCommunity/RxSwiftExt/blob/master/circle.yml#L26-L28

3. That's it! With your script set-up correctly, push a commit with an updated Podspec for your new version, followed by creating a new GitHub Release with a new tag name using semantic versioning. 

![Creating a new Release](https://i.imgur.com/qHp7ayA.png)

Your CI should automatically detect it and start building your repo: 

![Circle CI automatically detects & builds your release](https://i.imgur.com/FG2ris0.png)

If you've done everything correctly, your CI's last step should look something like this:

![Successful Deploy](https://i.imgur.com/G7jMOzr.png)

## CELEBRATE!

<p align="center">
  <b>Great work! All done :)</b><br />
  🎉🎉🎉🎉🎉🎉🎉<br />
  <img src="https://media.giphy.com/media/NeKB8ZR67TuV2/giphy.gif" />
</p>
