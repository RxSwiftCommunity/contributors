RxSwiftCommunity Contributors
=============================

We adhere to [Moya Contributor Guidelines v1.0.0](https://github.com/Moya/contributors/tree/1.0.0). 

tl;dr

- Contributors get added to the organization (with push access) after a single merged pull request.
- No pressure, though! Contributing to open source should never feel like a burden.
- Pull requests are always peer reviewed.
- If it feels right, merge. We can always revert later if we need to.
- We aim for public discussion.

The community also has discussions in Slack, too, so not all info is available in issues. You're welcome to [join the conversation](https://rxswift.slack.com).

One important point: RxSwiftCommunity is not the same as RxSwift. We're an organization for community-based projects _using_ RxSwift, and our contributor guidelines may differ.

Stewarding a Project
--------------------

If you have a project that you think belongs under the RxSwiftCommunity organization, please [open an issue](https://github.com/RxSwiftCommunity/contributors/issues/new). Generally, projects should be production-ready and able to be installed with CocoaPods or Carthage.

### Checklist for Transferring Ownership

When you open an issue, you can copy & paste the following checklist into the description or a comment to track progress:

```
- [ ] replace copyright with "Copyright (c) RxSwiftCommunity" in code
- [ ] replace copyright in README
- [ ] replace copyright in LICENSE
- [ ] update the remote URL of the Podspec (if any)
- [ ] update CI badge
- [ ] update CI settings
- [ ] transfer repository ownership (once you're a contributor)
- [ ] fork the repo back to your personal account
- [ ] add project to https://github.com/RxSwiftCommunity/rxswiftcommunity.github.io
- [ ] Add `community@rxswift.org` as an owner of your project's CocoaPod by using `pod trunk add-owner YourPodName community@rxswift.org`.
```

Code of Conduct
---------------

We have our own [Code of Conduct](Code%20of%20Conduct.md), which is adapted from the [Contributor Covenant](http://contributor-covenant.org), version 1.3.0, available at [http://contributor-covenant.org/version/1/3/0/](http://contributor-covenant.org/version/1/3/0/). The CoC is taken seriously by the project owners.

Automatic PR Checking with Peril
--------------------------------

[Peril](https://github.com/Danger/Peril) is a server which runs [Danger-JS](http://danger.systems/js/) automatically, on all pull requests, organization-wide. The rules for our Peril server are [here](https://github.com/RxSwiftCommunity/peril#automatic-pr-checking-with-peril), and we encourage everyone to think about new ways we could use Peril and Danger.

Setting up Automatic Deploys for your project
-----------------------------------------------

You might want to set up automatic deploys so that a new Podspec is pushed to CocoaPods whenever you push a new GitHub release.
This is already being done across many projects in the community successfully.

Interested? Check out the [Automatic Deploy Guide](Automatic%20Deploys.md) !
