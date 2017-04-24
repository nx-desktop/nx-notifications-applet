set(notificationsapplet_SRCS
    notificationsapplet.cpp
)

add_library(nomad_applet_notifications MODULE ${notificationsapplet_SRCS})

kcoreaddons_desktop_to_json(nomad_applet_notifications ../package/metadata.desktop)

target_link_libraries(nomad_applet_notifications
                      KF5::WindowSystem
                      KF5::Plasma
                      KF5::ConfigCore)

install(TARGETS nomad_applet_notifications DESTINATION ${PLUGIN_INSTALL_DIR}/plasma/applets)
