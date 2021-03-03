# termux-x11-addon-packages
Disabled packages from Termux X11 repo needed for Termux X11 addon by @twaik 

Termux-x11 addon istall instructions:

Install X11 addon .apk file which I mirrored in this repo

Because all termux apks must be signed with same signature, we need to use apk-signer, Google play: https://play.google.com/store/apps/details?id=com.haibison.apksigner

Therefore, we have to delete the main Termux app, in order to reinstall it signed with our key, don't worry, you can backup Termux data following this manual: https://wiki.termux.com/wiki/Backing_up_Termux

Download latest termux apk from F-droid: https://f-droid.org/en/packages/com.termux/

Open apk-signer and sign both downloaded Termux apk and X11 addon apk

Install signed apk files

Open Termux, and run:

pkg up
git clone https://github.com/digitalmadness/termux-x11-addon-packages
cd termux-x11-addon-packages
pkg in  ./ca-certificates-java_20210125_all.deb ./ca-certificates_20210125_all.deb ./libwayland-protocols_1.17-4_aarch64.deb ./libwayland-static_1.17.0-6_aarch64.deb ./libwayland_1.17.0-6_aarch64.deb ./xcb-proto_1.14.1_all.deb ./xkeyboard-config_2.31-2_all.deb ./xorg-util-macros_1.19.3_all.deb ./xorgproto_2020.1-1_all.deb ./xtrans_1.4.0-8_all.deb ./xwayland_1.20.5-6_aarch64.deb ./termux-x11_1.0-2_aarch64.deb

X11 addon is installed, you can run it with:

termux-x11&
export DISPLAY=:0
xfce4-session

Now we can configure shortcut for easy launch (In order to use shortcuts featture, you need Termux:widget addon, get it from here: https://f-droid.org/en/packages/com.termux.widget/ )

Run in Termux:

mkdir ~/.shortcuts
mv ~./termux-x11-addon-packages/Desktop.sh ~/.shortcuts
