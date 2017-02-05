#Build
sh msbuild.sh ../src/System.Configuration.ConfigurationManager/tests/System.Configuration.ConfigurationManager.Tests.csproj

#Build and test Linux
sh msbuild.sh /t:buildandtest -v:d ../src/System.Configuration.ConfigurationManager/tests/System.Configuration.ConfigurationManager.Tests.csproj

#Explore test results
firefox ../bin/AnyOS.AnyCPU.Debug/System.Configuration.ConfigurationManager.Tests/netstandard/testResults.xml

#Build and test Windows
msbuild.cmd /t:buildandtest ..\src\System.Configuration.ConfigurationManager\tests\System.Configuration.ConfigurationManager.Tests.csproj

