Build test with *build-tests.sh*  
Run individual test (System.Configuration.ConfigurationManager.Tests as example):  
  1. Navigate to corefx/bin/AnyOS.AnyCPU.Debug/System.Configuration.ConfigurationManager.Tests/netstandard
  2. Run corefx/bin/AnyOS.AnyCPU.Debug/System.Configuration.ConfigurationManager.Tests/netstandard$ /home/paul/github/coref
x/Tools/testdotnetcli/dotnet xunit.console.netcore.exe System.Configuration.ConfigurationManager.Tests.dll -xml testResults.xml -notrait Benchmark=true -notrait category=nonnetcoreapp1.1tests -notrait category=OuterLoop -notrait category=failing -notrait category=nonlinuxtests
