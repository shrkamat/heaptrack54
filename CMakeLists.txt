cmake_minimum_required(VERSION 3.19)

project (heaptrack-super-build)

include(ExternalProject)

# config
set (CMAKE_INSTALL_PREFIX /NDS)
set (QT_DIR /NDS)

#ExternalProject_Add(
#    openssl
#    URL https://www.openssl.org/source/old/1.0.2/openssl-1.0.2u.tar.gz
#    CONFIGURE_COMMAND ./config -shared --prefix=${CMAKE_INSTALL_PREFIX}
#    BUILD_IN_SOURCE 1
#)
#
#set(QT5_CONFIG
#    -release;
#    -verbose;
#    -opensource;
#    -confirm-license;
#    -shared;
#    -opengl es2;
#    -nomake examples;
#    -nomake tests;
#    -no-audio-backend;
#    -no-cups;
#    -no-pch;
#    -no-xcb;
#    -qt-libjpeg;
#    -qt-libpng;
#    -no-reduce-relocations;
#    -no-reduce-exports;
#    -system-zlib;
#    -no-icu -dbus;
#    -no-openssl;
#    -qt-xcb;
#    -no-fontconfig;
#    -qt-freetype;
#    -system-harfbuzz;
#    -openssl-linked;
#    -I${CMAKE_INSTALL_PREFIX}/include;
#    -L${CMAKE_INSTALL_PREFIX}/lib;
#)
#
#ExternalProject_Add(
#    qt5
#    DEPENDS openssl
#    GIT_REPOSITORY git@github.com:qt/qt5.git
#    GIT_TAG 5.6
#    GIT_SUBMODULES qtbase qtmultimedia qtimageformats qtsvg qtgraphicaleffects qtdeclarative qtscript qttools qtx11extras
#    CONFIGURE_COMMAND ./configure -prefix ${CMAKE_INSTALL_PREFIX} ${QT5_CONFIG}
#    INSTALL_COMMAND make install
#    BUILD_IN_SOURCE 1
#)
#
#ExternalProject_Add(
#    kitemmodels
#    DEPENDS qt5
#    GIT_REPOSITORY git@github.com:KDE/kitemmodels.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    threadweaver
#    DEPENDS kitemmodels
#    GIT_REPOSITORY git@github.com:KDE/threadweaver.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kconfig
#    DEPENDS threadweaver
#    GIT_REPOSITORY git@github.com:KDE/kconfig.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kcoreaddons
#    DEPENDS kconfig
#    GIT_REPOSITORY git@github.com:KDE/kcoreaddons.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kcodecs
#    DEPENDS kcoreaddons
#    GIT_REPOSITORY git@github.com:KDE/kcodecs.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kguiaddons
#    DEPENDS kcodecs
#    GIT_REPOSITORY git@github.com:KDE/kguiaddons.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kwidgetsaddons
#    DEPENDS kguiaddons
#    GIT_REPOSITORY git@github.com:KDE/kwidgetsaddons.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kauth
#    DEPENDS kwidgetsaddons
#    GIT_REPOSITORY git@github.com:KDE/kauth.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    ki18n
#    DEPENDS kauth
#    GIT_REPOSITORY git@github.com:KDE/ki18n.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kconfigwidgets 
#    DEPENDS ki18n
#    GIT_REPOSITORY git@github.com:KDE/kconfigwidgets.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kwindowsystem 
#    DEPENDS kconfigwidgets
#    GIT_REPOSITORY git@github.com:KDE/kwindowsystem.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kdbusaddons 
#    DEPENDS kwindowsystem
#    GIT_REPOSITORY git@github.com:KDE/kdbusaddons.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kcrash 
#    DEPENDS kdbusaddons
#    GIT_REPOSITORY git@github.com:KDE/kcrash.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kservice 
#    DEPENDS kcrash
#    GIT_REPOSITORY git@github.com:KDE/kservice.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    karchive
#    DEPENDS kservice
#    GIT_REPOSITORY git@github.com:KDE/karchive.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kitemviews
#    DEPENDS karchive 
#    GIT_REPOSITORY git@github.com:KDE/kitemviews.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kiconthemes
#    DEPENDS kitemviews 
#    GIT_REPOSITORY git@github.com:KDE/kiconthemes.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kcompletion 
#    DEPENDS kiconthemes 
#    GIT_REPOSITORY git@github.com:KDE/kcompletion.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    sonnet 
#    DEPENDS kcompletion 
#    GIT_REPOSITORY git@github.com:KDE/sonnet.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    ktextwidgets 
#    DEPENDS sonnet 
#    GIT_REPOSITORY git@github.com:KDE/ktextwidgets.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    attica 
#    DEPENDS ktextwidgets 
#    GIT_REPOSITORY git@github.com:KDE/attica.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kglobalaccel 
#    DEPENDS attica 
#    GIT_REPOSITORY git@github.com:KDE/kglobalaccel.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kxmlgui 
#    DEPENDS kglobalaccel
#    GIT_REPOSITORY git@github.com:KDE/kxmlgui.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)
#
#ExternalProject_Add(
#    kbookmarks
#    DEPENDS kxmlgui 
#    GIT_REPOSITORY git@github.com:KDE/kbookmarks.git
#    GIT_TAG v5.36.0
#    CMAKE_ARGS
#      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
#)

ExternalProject_Add(
    kjobwidgets
#    DEPENDS kxmlgui
    GIT_REPOSITORY git@github.com:KDE/kjobwidgets.git
    GIT_TAG v5.36.0
    CMAKE_ARGS
      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
)

ExternalProject_Add(
    kio 
    DEPENDS kjobwidgets
    GIT_REPOSITORY git@github.com:KDE/kio.git
    GIT_TAG v5.36.0
    CMAKE_ARGS
      -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
      -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX}
)

#ExternalProject_Add(
#    kchart
#    DEPENDS KConfigWidgets
#    GIT_REPOSITORY git@github.com:KDE/kdiagram.git
#    GIT_TAG v2.6.0
#    CMAKE_ARGS
#        -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#        -DCMAKE_PREFIX_PATH:PATH=${QT_DIR}
#)
#
#ExternalProject_Add(
#    heaptrack
#    DEPENDS kchart
#    GIT_REPOSITORY git@github.com:KDE/heaptrack.git
#    GIT_TAG v1.1.0
#    PATCH_COMMAND patch -p1 < ${CMAKE_CURRENT_SOURCE_DIR}/patches/missing_boost_includes.patch
#    CMAKE_ARGS
#        -DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_INSTALL_PREFIX}
#        -DBOOST_ROOT=/home/skamath/proactive/c++/boost/out
#        -DCMAKE_PREFIX_PATH:PATH=${CMAKE_INSTALL_PREFIX};${QT_DIR}
#)

# REFS
# ====
# https://github.com/pyke369/sffmpeg/blob/master/CMakeLists.txt
# https://github.com/smistad/FAST/blob/master/cmake/ExternalQt5.cmake
