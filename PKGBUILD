# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname="nemo-gst-interfaces"
pkgver=0.20200911.0+3+g142f012
pkgrel=1
_commit=142f01211fedfa094052be7c207aa4f7102b05e1
pkgdesc="This directory contains Nemo mobile specific GStreamer interfaces"
arch=("i686" "x86_64" "aarch64")
url="https://github.com/droidian/nemo-gst-interfaces"
license=("LGPL-2.1")
makedepends=("gstreamer" "gst-plugins-base")
source=("git+https://github.com/droidian/nemo-gst-interfaces#commit=${_commit}")
sha256sums=("SKIP")
options=("!emptydirs")

pkgver() {
  cd "${srcdir}/${pkgname}"
  git describe --tags | sed 's/^v//;s/-/+/g;s|pureos/||g;s|droidian/||g;s|bookworm/||g'
}

build() {
    cd ${pkgname}
    ./autogen.sh
    ./configure --prefix=/usr
    make -j$(nproc)
}

package() {
    cd ${pkgname}
    make DESTDIR="${pkgdir}" install
}
