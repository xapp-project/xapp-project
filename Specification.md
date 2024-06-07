# XApp Specification

TBD: I suppose it would be nice to call the project XApp instead of xapp ? (used lower case for now)

In order to be shown on the xapp project, applications need to fulfill a list of requirements. This specification is used in order to summarize these requirements and as such can be utilized to decide if an application can join the xapp project.

## Requirements

### Licensing

Xapps need to be licensed on a [FOSS license](https://opensource.org/licenses).

### Operating System

Xapps need to be able to run in a Linux environment. The support of other operating systems is optional.

### Graphical Desktop Application

This project targets graphical applications which run on desktop systems and dependencies of them. E.g. console applications, kernel-modules and system-services cannot be xapps.

### Usage of standards

In order to be desktop-environment agnostic, the compliance to the following [freedesktop.org](https://www.freedesktop.org) standards is mandatory to be listed as an xapp:

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

Applications which are part of the xapp project should support server side window decorations and use them by default. Xapps are free to optionally as well support client side decorations [^1].

### Menus

If menus are required for a xapps, traditional menu bars should be used by default. It is fine to optionally support e.g. hamburger menus [^2].

TBD: Do we want to force a default on this?

### Theming

User theming has to be supported by xapps (TODO: Where is the spec for general theming?) [^3]

### Desktop Environment Agnostic

If the same windowing, theme and icon theme is used, XApps are supposed to look the same on each Linux desktop environment they run on. As such, they should not have dependencies to desktop-specific styles.

### Identification as xapp application

If an application fulfills all above criteria and is supposed to be added to the xapp project, it has to add a paragraph to a README.md file located on the top level of its git project with the following text:

> ## Xapp compliance
>
> This application follows the standards defined in the [Xapp specification v1.0.0](insert link here) and as such will run fine on linux desktop environments which support freedesktop.org standards. The UI of this application will be well integrated on desktop environments which support the xapp standard.

The xapp project provides a set of [project-properties](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization) which allows to filter xapps for supported operating systems, the used license, the used toolkit and supported display servers. Please set these project-properties for your project accordingly.  

### Repository Location

Once an application is approved as a xapp application, it either is hosted directly by the Xapp project (so that the native issue tracker, git repository and infrastructure is used) or its repository is mirrored to the xapp project. On choosing the latter, the xapp project page will hide the possibility to file issues and show a link to the original repository location.

## Violations

If an application which is listed as xapp violates one of the above requirements, the xapp staff can drop if from the xapps project. As such, the application should not advertise itself as a xapp compliant application anymore.

[^1]: Using server side decorations for applications enables users to have more control on window decorations and allows them to share the same decoration-style across installed applications. Whereas, applications using client side decorations can look very out of place by forcing a different set and style of window buttons on foreign locations, leading to style fragmentation and a poor user experience. We want to have a good user experience by default and as such request the usage of server side decorations as default for xapps.

[^2]: TBD: Why menubars

[^3]: Point to concrete theming guidelines ... we really should have a XDG spec for this

