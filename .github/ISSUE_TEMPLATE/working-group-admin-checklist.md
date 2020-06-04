---
name: Working Group Admin Checklist
about: This issue is to track maintenance and migration of repos to IPR manager
title: Migrating from CG to WG
labels: ''
assignees: ''

---

Use the repo IPR manager to ease the transition of deliverables to the Working Group and keep track of the origins of contributions. If you are adding a new repository, please create it directly using [Repository Manager](https://labs.w3.org/repo-manager/). For the existing repositories make sure to track the following checklist:

- [ ] Add **LICENSE.md**.
  * [WG-LICENSE.md](https://github.com/w3c/licenses/blob/master/WG-LICENSE.md) for specs under the W3C Document License.
  * [WG-LICENSE-SW.md](https://github.com/w3c/licenses/blob/master/WG-LICENSE-SW.md) for specs under the W3C Software and Document License.
- [ ] Add **CONTRIBUTING.md**
  * [WG-CONTRIBUTING.md]() 
- [ ] Add [w3c.json](https://w3c.github.io/w3c.json.html)
  * List administrative contacts.
  * Add group id: 87846 for immersive-web groups.
- [ ] Add an **index.html** that's a [bare-bones ReSpec spec](https://github.com/w3c/ash-nazg/blob/master/templates/index.html) ready to be edited.
- [ ] Add [README.md](https://github.com/w3c/ash-nazg/blob/master/templates/CODE_OF_CONDUCT.md).
- [ ] Add [CODE_OF_CONDUCT.md](https://github.com/immersive-web/webxr/blob/master/CODE_OF_CONDUCT.md).
- [ ] **Import repository** in the [IPR manager tool](https://labs.w3.org/repo-manager/). 
- [ ] Ask the group participants and contributors to [associate their GitHub accounts with their W3C accounts](https://www.w3.org/users/myprofile/connectedaccounts) within 2 weeks. 

Once the Repository Manager is activated, it will interact with Github pull requests. 

- [ ] Contributions from Github accounts not associated with a W3C account gets flagged with a warning. Manually approve the flagged warnings via the Repository Manager.
- [ ] Count as contributors, not just the person making the pull request, but also anyone added either in the PR description or in any subsequent comment using "+@username" *on a line on its own*. If a contributor was added by mistake, she can be removed with "-@username" *on a line on its own*.

Learn more or report bugs to the [tool repository](https://github.com/w3c/ash-nazg).
