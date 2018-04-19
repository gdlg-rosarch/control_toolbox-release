# Script generated with Bloom
pkgdesc="ROS - The control toolbox contains modules that are useful across all controllers."
url='http://ros.org/wiki/control_toolbox'

pkgname='ros-lunar-control-toolbox'
pkgver='1.16.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin>=0.5.68'
'ros-lunar-cmake-modules'
'ros-lunar-control-msgs'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-message-generation'
'ros-lunar-realtime-tools'
'ros-lunar-roscpp'
'ros-lunar-std-msgs'
'tinyxml'
)

depends=('ros-lunar-cmake-modules'
'ros-lunar-control-msgs'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-message-runtime'
'ros-lunar-realtime-tools'
'ros-lunar-roscpp'
'ros-lunar-std-msgs'
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
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

