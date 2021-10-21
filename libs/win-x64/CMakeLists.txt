set(PhysXSDK PhysX PhysXCommon PhysXFoundation PhysXExtensions PhysXCooking PhysXCharacterKinematic PhysXVehicle PhysXPvdSDK)
foreach(PX IN LISTS PhysXSDK)
    add_library(${PX} STATIC IMPORTED GLOBAL)
    set_target_properties(${PX} PROPERTIES
      IMPORTED_LOCATION_DEBUG ${CMAKE_CURRENT_LIST_DIR}/debug/${PX}_static_64.lib
      IMPORTED_LOCATION_DEV ${CMAKE_CURRENT_LIST_DIR}/debug/${PX}_static_64.lib
      IMPORTED_LOCATION_RELEASE ${CMAKE_CURRENT_LIST_DIR}/release/${PX}_static_64.lib
    )
endforeach()