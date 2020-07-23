### Patch STM32CubeMx to generate 4 spaces tab instead of 2 spaces tab

Manual procedure:
```
# find your STM32CubeMX.jar, make backup if necessary
find /opt/st/stm32cubeide STM32CubeMX.jar
 
# copy to temporary directory
cp STM32CubeMX.jar /tmp/test
 
# download Java Jar explorer and decompiler
https://github.com/Col-E/Recaf

# use recaf to navigate to com/st/microxplorer/codegenerator/CodeEngine.class
# may need to switch to different parser if got parsing error !

search for replace("#t", "  "), right click to the containing function "cleanCode", find for string "   ", change to "    "
 
# save the new jar file by File > Export Program
# close recaf, double check by reopen new jar file and confirm #t is now 4 spaces.
 
# restore new STM32CubeMX.jar to the original location
```