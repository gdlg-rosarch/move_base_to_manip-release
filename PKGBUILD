# Script generated with Bloom
pkgdesc="ROS - Move the robot base until a desired end-effector pose can be reached."
url='http://wiki.ros.org/move_base_to_manip'

pkgname='ros-kinetic-move-base-to-manip'
pkgver='1.0.18_2'
pkgrel=1
arch=('any')
license=('See license.txt'
)

makedepends=('eigen3'
'ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-interactive-markers'
'ros-kinetic-message-generation'
'ros-kinetic-message-runtime'
'ros-kinetic-move-base-msgs'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-ros-planning-interface'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-tf2-geometry-msgs'
'ros-kinetic-visualization-msgs'
)

depends=('eigen3'
'ros-kinetic-geometry-msgs'
'ros-kinetic-interactive-markers'
'ros-kinetic-message-generation'
'ros-kinetic-message-runtime'
'ros-kinetic-move-base-msgs'
'ros-kinetic-moveit-core'
'ros-kinetic-moveit-ros-planning-interface'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-tf2-geometry-msgs'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=move_base_to_manip
source=()
md5sums=()

prepare() {
    cp -R $startdir/move_base_to_manip $srcdir/move_base_to_manip
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

