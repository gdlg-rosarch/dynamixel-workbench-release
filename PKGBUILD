# Script generated with Bloom
pkgdesc="ROS - This package is composed of 'dynamixel_item', 'dynamixel_tool', 'dynamixel_driver' and 'dynamixel_workbench' class. The 'dynamixel_item' is saved as control table item and information of Dynamixels. The 'dynamixel_tool' class loads its by model number of Dynamixels. The 'dynamixel_driver' class includes wraped function used in DYNAMIXEL SDK. The 'dynamixel_workbench' class make simple to use Dynamixels"
url='http://wiki.ros.org/dynamixel_workbench_toolbox'

pkgname='ros-kinetic-dynamixel-workbench-toolbox'
pkgver='0.2.4_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-dynamixel-sdk'
'ros-kinetic-roscpp'
)

depends=('ros-kinetic-dynamixel-sdk'
'ros-kinetic-roscpp'
)

conflicts=()
replaces=()

_dir=dynamixel_workbench_toolbox
source=()
md5sums=()

prepare() {
    cp -R $startdir/dynamixel_workbench_toolbox $srcdir/dynamixel_workbench_toolbox
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

