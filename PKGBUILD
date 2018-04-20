# Script generated with Bloom
pkgdesc="ROS - Dynamixel-Workbench is dynamixel solution for ROS. This metapackage allows you to easily change the ID, baudrate and operating mode of the Dynamixel. Furthermore, it supports various controllers based on operating mode and Dynamixel SDK. These controllers are commanded by operators."
url='http://wiki.ros.org/dynamixel_workbench'

pkgname='ros-kinetic-dynamixel-workbench'
pkgver='0.2.4_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-dynamixel-workbench-controllers'
'ros-kinetic-dynamixel-workbench-operators'
'ros-kinetic-dynamixel-workbench-single-manager'
'ros-kinetic-dynamixel-workbench-single-manager-gui'
'ros-kinetic-dynamixel-workbench-toolbox'
)

conflicts=()
replaces=()

_dir=dynamixel_workbench
source=()
md5sums=()

prepare() {
    cp -R $startdir/dynamixel_workbench $srcdir/dynamixel_workbench
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

