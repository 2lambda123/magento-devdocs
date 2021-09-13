---
title: Release policy
group: release
---

{{site.data.var.ee}} and {{site.data.var.ce}} use [semantic versioning](https://semver.org/) on the individual module level (for example `magento/framework 101.1.1`), but not for the marketing version number. For example:

-  **MAJOR release**—2
-  **MINOR release**—2.4
-  **PATCH release**—2.4.1
   -  **SECURITY patch release**—2.4.1-p1
      -  Security bug fix
      -  Security enhancement
-  **Feature release**
-  **Hotfix**
-  **Individual patch**
-  **Custom patch**

## MINOR release

The following guidelines apply to minor releases:

-  Breaking changes are possible; code written for {{site.data.var.ee}} 2.2.x may no longer work with {{site.data.var.ee}} 2.3.x. For example, minor releases can introduce support for major system requirements and dependencies, such as PHP.
-  Module versions can vary. For example, some module changes are introduced in a new patch whereas others are introduced in a minor release.
-  Minor releases can include new features that may require additional work by you or your solution partner during upgrade to ensure compatibility.
-  Minor releases can include fixes for security and quality issues.

## PATCH release

Patch releases are primarily focused on delivering security and high-priority quality fixes to help you keep your sites performing at their peak.

The following guidelines apply to patch releases:

-  The latest-supported minor release will receive full functional quality fixes and enhancements.
-  Changes that could break extensions or code compatibility are avoided. For example, code written for version 2.2.0 should still work on version 2.2.7.
-  On an exceptional basis, breaking changes or additional patches or hotfixes may be released to address security or compliance issues and high-impact quality issues. On the module level, these are mostly PATCH-level changes; sometimes MINOR-level changes.
-  Patch releases may include new features as long as they are not expected to break other code. New feature can be included in core code, as an extension (like Page Builder), or as an independent feature (like Live Search and Product Recommendations).

## SECURITY patch release

**Security Bug Fix**: A software code change that resolves an identified security issue and delivers expected results in an affected product area. These fixes are generally backward compatible.

**Security Enhancement**: A software improvement or configuration change to proactively improve security within the application. These security enhancements help address security risks that impact the security posture of the {{site.data.var.ee}} application but may be backward incompatible.

With security patch releases, you can keep your site more secure without applying additional quality fixes and enhancements that are contained within a full quarterly patch release. Security patch releases are appended with ‘-pN’, where N is the incremental patch version beginning with 1 (for example, 2.3.5-p1). Security patch releases can also include hotfixes required to address critical issues that affect the {{site.data.var.ee}} application.

Each security patch release is based on the prior full patch release, hence it contains quality and security fixes from prior patch release and security fixes created between the prior full patch release and the security patch release.

With the announcement of our [updated life cycle policy](https://magento.com/blog/updated-lifecycle-policy-magento-releases) [10/1/2020], our security patch releases are differentiated based on whether they are applicable to the latest-supported minor release or a part of a still-supported previous minor release line:

-  **Security patch releases for the latest-supported minor release**:

   -  The security patch release for the latest-supported minor release (currently {{site.data.var.ee}} 2.4) includes:

      -  Security bug fixes that have been created since the previous full patch release.

      -  These security patch releases can also include hotfixes required to address critical issues that may affect the {{site.data.var.ee}} application.

   -  The security patch release for the latest-supported minor release (currently {{site.data.var.ee}} 2.4) does not typically include security enhancements. Instead, these are included in the full comprehensive patch release for the latest-supported minor release.

-  **Security patch releases for supported previous minor releases**:

   -  The security patch release for a previous minor release that is still supported (currently {{site.data.var.ee}} 2.3) includes:

      -  Security bug fixes that have been created since the previous patch or security patch release, as well as new security enhancements.

      -  These security patch releases can also include hotfixes required to address critical issues that affect the {{site.data.var.ee}} application.

      |                                                                                | Security Bug | Security Enhancement |
      |--------------------------------------------------------------------------------|--------------|----------------------|
      | Security patch releases for the latest-supported minor release (currently 2.4) | X            |                      |
      | Security patch releases for previous, supported minor releases (currently 2.3) | X            | X                    |

For general information about security releases, see [Introducing the New Security-only Patch Release](https://community.magento.com/t5/Magento-DevBlog/Introducing-the-New-Security-only-Patch-Release/ba-p/141287). For instructions on downloading and applying security patches, see [Quick start install]({{ site.baseurl }}/guides/v2.3/install-gde/composer.html).

## Feature release

Feature releases contain new features and feature updates that are delivered as independent services, separate from the patch releases. Examples include services like Product Recommendations and Live Search, independent modules like PWA Studio and Inventory Management (MSI), and updates to our cloud services and infrastructure.

## Hotfix

Hotfixes are patches that contain high-impact security or quality fixes that affect a large number of merchants. These fixes are applied to the next patch release for the applicable minor version. Adobe releases hotfixes for {{site.data.var.ee}} as needed.

{:.bs-callout-info}
Hotfixes can contain backward incompatible changes.

## Individual patch

Individual patches contain low-impact quality fixes for a specific issue. These fixes are applied to the supported minor versions of {{site.data.var.ee}}. Adobe releases individual patches as needed for {{site.data.var.ee}} in accordance with our [Software Lifecycle Policy](https://magento.com/sites/default/files/magento-software-lifecycle-policy.pdf).

{:.bs-callout-info}
Individual patches do not contain backward incompatible changes.

## Custom patch

Created by non-Adobe personnel to fix an issue or modify the {{site.data.var.ee}} code for various reasons. Custom patches are delivered through the [Quality Patches Tool]({{ site.baseurl }}{{ site.gdeurl }}/comp-mgr/patching/mqp.html).

{:.ref-header}
Related topics

-  [Planning and Budgeting for Commerce Upgrade Cycles](https://magento.com/sites/default/files8/2019-08/Magento-Release-Cycle-Infosheet_Aug_2019.pdf)
-  [Versioning]({{ site.baseurl }}/guides/v2.3/extension-dev-guide/versioning/).
-  [Upcoming releases]({{ site.baseurl }}/release/)
