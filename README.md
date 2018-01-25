
    cd targets
    dotnet pack -o ../nupkgs -c Release

    cd consumer
    dotnet nuget locals all --clear
    dotnet restore --force --no-cache

    dotnet msbuild /t:MyTest
    dotnet targets

    dotnet msbuild /pp > full-msbuild.xml
