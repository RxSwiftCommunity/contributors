RxSwiftCommunity Contributors
=============================

We adhere to [Moya Contributor Guidelines v1.0.0](https://github.com/Moya/contributors/tree/1.0.0). 

tl;dr

- Contributors get added to the organization (with push access) after a single merged pull request.
- No pressure, though! Contributing to open source should never feel like a burden.
- Pull requests are always peer reviewed.
- If it feels right, merge. We can always revert later if we need to.
- We aim for public discussion.

The community also has discussions in Slack, too, so not all info is available in issues. You're welcome to [join the conversation](http://slack.rxswift.org).

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
```

Code of Conduct
---------------

We have our own [Code of Conduct](Code of Conduct.md), which is adapted from the [Contributor Covenant](http://contributor-covenant.org), version 1.3.0, available at [http://contributor-covenant.org/version/1/3/0/](http://contributor-covenant.org/version/1/3/0/). The CoC is taken seriously by the project owners.

Automatic PR Checking with Peril
--------------------------------

[Peril](https://github.com/Danger/Peril) is a server which runs [Danger-JS](http://danger.systems/js/) automatically, on all pull requests, organization-wide. It can check for pull request metadata, commit information, which files were changed, all kinds of things. Here are the things Peril checks on _every_ RxSwiftCommunity repo's pull requests:

- Ensuring that changes to non-test code are reflected in the changelog (if one exists). [PR](https://github.com/RxSwiftCommunity/peril/pull/1)

If you have an idea for something we should check for in a pull request, or if you have an idea to improve the community using Peril to respond to issues, please [open an issue](https://github.com/RxSwiftCommunity/contributors/issues/new) so we can discuss!

Our Peril settings are hosted [here](https://github.com/RxSwiftCommunity/peril). [@ashfurrow](https://github.com/ashfurrow) is the point person for Peril, ping him if you run into any issues.
