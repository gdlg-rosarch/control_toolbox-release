# Script generated with Bloom
pkgdesc="ROS - The control toolbox contains modules that are useful across all controllers."
url='http://ros.org/wiki/control_toolbox'

pkgname='ros-kinetic-control-toolbox'
pkgver='1.16.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin>=0.5.68'
'ros-kinetic-cmake-modules'
'ros-kinetic-control-msgs'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-message-generation'
'ros-kinetic-realtime-tools'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'tinyxml'
)

depends=('ros-kinetic-cmake-modules'
'ros-kinetic-control-msgs'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-message-runtime'
'ros-kinetic-realtime-tools'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'tinyxml'
)

conflicts=()
replaces=()

_dir=control_toolbox
source=()
md5sums=()

prepare() {
    cp -R $startdir/control_toolbox $srcdir/control_toolbox
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

