# XApp Specification

In order to be shown on the XApp project, applications need to fulfill a list of requirements. This specification is used in order to summarize these requirements and as such can be utilized to decide if an application can join the XApp project.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119).

## Requirements

### Licensing

XApps SHALL be licensed under an [OSI-approved license](https://opensource.org/licenses).

### Operating System

XApps MUST be able to run in a Linux environment. Support for other operating systems is welcome, though optional.

### Usage of standards

In order to be desktop-environment agnostic, XApps MUST comply with the following [freedesktop.org](https://www.freedesktop.org) standards when they apply to functionality included in the application.

- [Xdg Autostart](https://www.freedesktop.org/wiki/Specifications/autostart-spec/)
- [Xdg Base Directories](https://www.freedesktop.org/wiki/Specifications/basedir-spec/)
- [Xdg Desktop Entry](https://www.freedesktop.org/wiki/Specifications/desktop-entry-spec/)
- [Xdg Desktop Menus](https://www.freedesktop.org/wiki/Specifications/menu-spec/)
- [File Manager DBUS interface](https://www.freedesktop.org/wiki/Specifications/file-manager-interface/)
- [File URI Specification](https://www.freedesktop.org/wiki/Specifications/file-uri-spec/)
- [Free Media Player Specification](https://www.freedesktop.org/wiki/Specifications/free-media-player-specs/)
- [Free Media Player Remote Interface Specification](https://www.freedesktop.org/wiki/Specifications/mpris-spec/)
- [Xdg Icon Theme](https://www.freedesktop.org/wiki/Specifications/icon-theme-spec/)
- [Xdg Icon Naming](https://www.freedesktop.org/wiki/Specifications/icon-naming-spec/)
- [Shared mime Database](https://www.freedesktop.org/wiki/Specifications/shared-mime-info-spec/)
- [Startup Notification](https://www.freedesktop.org/wiki/Specifications/startup-notification-spec/)
- [Trashcan support](https://www.freedesktop.org/wiki/Specifications/trash-spec/)
- [Bookmark Interchange Format](https://pyxml.sourceforge.net/topics/xbel/)

TBD: Not sure on these:
- [MIME Applications Associations](https://www.freedesktop.org/wiki/Specifications/mime-apps-spec/)
- [XSettings](https://www.freedesktop.org/wiki/Specifications/xsettings-spec/)
- [Cursor Conventions](https://www.freedesktop.org/wiki/Specifications/cursor-spec/)
- [Sound Theme](https://www.freedesktop.org/wiki/Specifications/sound-theme-spec/)

### Window decorations

XApp project applications MUST support server-side window decorations, where applicable, but MAY also support client-side decorations. If both are supported, the determination of which to use by default should follow user and environment preferences, falling back to server-side if no default can be determined. Applications MAY allow users to configure them to use either decoration model.

### Theming

User theming MUST be supported by XApps (TODO: Where is the spec for general theming?)

### Desktop Environment Agnostic

If the same windowing, theme and icon theme is used, XApps SHOULD be visually consistent across Linux desktop environments. As such, they MUST NOT have dependencies to desktop-specific styles.

### Localization

XApps SHALL support localization. As such, there needs to be a standardized way to add/modify translations. For user interactions XApps SHOULD automatically use the system defined locale when possible.

### Identification as XApp application

If an application fulfills all above criteria and is supposed to be added to the XApp project, it SHOULD add a paragraph to a README.md file located on the top level of its git project with the following text:

> ## XApp compliance
>
> This applications follows the standards defined in [version x.y.z of the XApp specification](insert link here), and should integrate well into any desktop environment that has adopted the XApp specification.

The XApp project provides a set of [project-properties](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization) which allows to filter XApps for supported operating systems, the used license, the used toolkit and supported display servers. Please set these project-properties for your project accordingly.  
### Communication

Maintainers of projects which comply to the XApps specification SHOULD idle in the [XApp Matrix channel](https://matrix.to/#/#xapp:matrix.org) in order to simplify communication.

### Repository Location

Once an application is approved as an XApp application, it is either hosted directly by the XApp project (so that the native issue tracker, git repository and infrastructure is used) or its repository is mirrored to the XApp project. On choosing the latter, the XApp project page will hide the possibility to file issues and show a link to the original repository location.

## Violations

If an application which is listed as XApp violates one of the above requirements, the XApp staff can drop if from the XApps project. As such, the application SHOULD NOT advertise itself as a XApp compliant application anymore.

