SET( SRC_PATH ../../../.. )
SET( SOURCES  ${SRC_PATH}/Tools/CmdLine/IccSpecSepToTiff/iccSpecSepToTiff.cpp
              ${SRC_PATH}/Tools/CmdLine/IccApplyProfiles/TiffImg.cpp )
SET( TARGET_NAME iccSpecSepToTiff )
INCLUDE_DIRECTORIES ( ${SRC_PATH}/Tools/CmdLine/IccApplyProfiles/ )

ADD_EXECUTABLE( ${TARGET_NAME} ${SOURCES} )
TARGET_LINK_LIBRARIES( ${TARGET_NAME} ${TARGET_LIB_ICCPROFLIB} ${TIFF_LIBRARY} )
IF(ENABLE_INSTALL_RIM)
  INSTALL (TARGETS ${TARGET_NAME} DESTINATION ${CMAKE_INSTALL_BINDIR})
ENDIF(ENABLE_INSTALL_RIM)
