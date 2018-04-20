# Script generated with Bloom
pkgdesc="ROS - This package is single manager for a Dynamixel. It provides a terminal environment to check the status of Dynamixel and control it before using Dynamixel"
url='http://wiki.ros.org/dynamixel_workbench_single_manager'

pkgname='ros-kinetic-dynamixel-workbench-single-manager'
pkgver='0.2.4_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-dynamixel-workbench-msgs'
'ros-kinetic-dynamixel-workbench-toolbox'
'ros-kinetic-roscpp'
)

depends=('ros-kinetic-dynamixel-workbench-msgs'
'ros-kinetic-dynamixel-workbench-toolbox'
'ros-kinetic-roscpp'
)

conflicts=()
replaces=()

_dir=dynamixel_workbench_single_manager
source=()
md5sums=()

prepare() {
    cp -R $startdir/dynamixel_workbench_single_manager $srcdir/dynamixel_workbench_single_manager
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

