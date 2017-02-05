###Build
sh msbuild.sh ../src/System.Configuration.ConfigurationManager/tests/System.Configuration.ConfigurationManager.Tests.csproj

###Build and test Linux
sh msbuild.sh /t:buildandtest -v:d ../src/System.Configuration.ConfigurationManager/tests/System.Configuration.ConfigurationManager.Tests.csproj

###Explore test results
firefox ../bin/AnyOS.AnyCPU.Debug/System.Configuration.ConfigurationManager.Tests/netstandard/testResults.xml

###Build and test Windows
msbuild.cmd /t:buildandtest ..\src\System.Configuration.ConfigurationManager\tests\System.Configuration.ConfigurationManager.Tests.csproj

###Coverage reports
msbuild /p:Coverage=true  
Results - corefx\bin\tests\coverage\index.htm
https://ci.dot.net/job/dotnet_corefx/job/master/job/code_coverage_windows/

###Debug Tests
danmosemsft commented on 3 Dec 2016
This is how I debug tests. Make sure VS is on the path (eg use a developer command prompt) then:

msbuild thetestproject.csproj /t:buildandtest /p:testdebugger=devenv.exe

When Xunit starts it will pop the debugger. First time around it will not guess the correct debug engine, you must open solution properties and change it to the Core debug engine (I am using VS2015) Now set your breakpoints and hit F5.

You can Save the solution and open that solution next time and F5 it will just work without need to reset debugger engine or breakpoints.
