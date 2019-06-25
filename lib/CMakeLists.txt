set(notificationsapplet_SRCS
    notificationsapplet.cpp
)

add_library(nx_applet_notifications MODULE ${notificationsapplet_SRCS})

kcoreaddons_desktop_to_json(nx_applet_notifications ../package/metadata.desktop)

target_link_libraries(nx_applet_notifications
                      KF5::WindowSystem
                      KF5::Plasma
                      KF5::ConfigCore)

install(TARGETS nx_applet_notifications DESTINATION ${PLUGIN_INSTALL_DIR}/plasma/applets)
