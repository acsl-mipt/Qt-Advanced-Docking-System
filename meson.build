project('ads', 'cpp')

qt5_mod = import('qt5')
qt5_dep = dependency('qt5', modules: ['Core', 'Gui', 'Widgets'])

defs = ['-DADS_SHARED_EXPORT', '-DQT_NO_DEBUG_OUTPUT']

moc_headers = [
    'src/ads_globals.h',
    'src/DockAreaWidget.h',
    'src/DockAreaTabBar.h',
#    'src/DockContainerWidget.h',
    'src/DockManager.h',
    'src/DockWidget.h',
    'src/DockWidgetTab.h',
    'src/FloatingDockContainer.h',
    'src/DockOverlay.h',
    'src/DockSplitter.h',
    'src/DockAreaTitleBar.h',
    'src/ElidingLabel.h',
]

src = [
    'src/ads_globals.cpp',
    'src/DockAreaWidget.cpp',
    'src/DockAreaTabBar.cpp',
    'src/DockContainerWidget.cpp',
    'src/DockManager.cpp',
    'src/DockWidget.cpp',
    'src/DockWidgetTab.cpp',
    'src/FloatingDockContainer.cpp',
    'src/DockOverlay.cpp',
    'src/DockSplitter.cpp',
    'src/DockAreaTitleBar.cpp',
    'src/ElidingLabel.cpp',
]  

rc_files = 'src/ads.qrc'

processed = qt5_mod.preprocess(
  qresources : rc_files,
  moc_headers : moc_headers,
)

ads_lib = shared_library('ads',
  sources : src + processed,
  cpp_args : defs,
  include_directories : include_directories('src'),
  dependencies : qt5_dep,
)

ads_dep = declare_dependency(
  link_with : ads_lib,
  include_directories : include_directories('src', is_system : true),
)

