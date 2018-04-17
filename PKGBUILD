# Script generated with Bloom
pkgdesc="ROS - rqt_service_caller provides a GUI plugin for calling arbitrary services."
url='http://wiki.ros.org/rqt_service_caller'

pkgname='ros-kinetic-rqt-service-caller'
pkgver='0.4.8_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('python2-rospkg'
'ros-kinetic-rosservice'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-py'
'ros-kinetic-rqt-py-common'
)

conflicts=()
replaces=()

_dir=rqt_service_caller
source=()
md5sums=()

prepare() {
    cp -R $startdir/rqt_service_caller $srcdir/rqt_service_caller
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

