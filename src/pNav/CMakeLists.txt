#--------------------------------------------------------
# The CMakeLists.txt for:                     pNav
# Author(s):                                  Anthony Spears
#--------------------------------------------------------

# Set System Specific Libraries
if (${WIN32})
  # Windows Libraries
  SET(SYSTEM_LIBS
     wsock32 )
  SET(RESOURCES icon1.ico pNav.rc) 
else (${WIN32})
  # Linux and Apple Libraries
  SET(SYSTEM_LIBS
      m
      pthread )
endif (${WIN32})

#what files are needed?
SET(SRC MOOSNavigator.cpp pNavMain.cpp MOOSPriorityInput.cpp MOOSNavigator.h MOOSPriorityInput.h ${RESOURCES})
    
ADD_EXECUTABLE(pNav ${SRC})

TARGET_LINK_LIBRARIES(pNav
   ${MOOS_LIBRARIES}
   ${SYSTEM_LIBS}
   MOOSNav
   newmat)
 
