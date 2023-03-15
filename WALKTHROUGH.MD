mkdir testTemplate
cd testTemplate
dotnet new sln
dotnet new webapi -o testTemplate.WebApi
dotnet new classlib -o testTemplate.Core
dotnet new classlib -o testTemplate.Domain
dotnet new classlib -o testTemplate.Infrastructure
dotnet new xunit -o testTemplate.Test

dotnet sln add testTemplate.WebApi/testTemplate.WebApi.csproj
dotnet sln add testTemplate.Core/testTemplate.Core.csproj
dotnet sln add testTemplate.Domain/testTemplate.Domain.csproj
dotnet sln add testTemplate.Infrastructure/testTemplate.Infrastructure.csproj
dotnet sln add testTemplate.Test/testTemplate.Test.csproj

dotnet add testTemplate.WebApi/testTemplate.WebApi.csproj reference testTemplate.Core/testTemplate.Core.csproj

dotnet add testTemplate.Core/testTemplate.Core.csproj reference testTemplate.Domain/testTemplate.Domain.csproj testTemplate.Infrastructure/testTemplate.Infrastructure.csproj

dotnet add testTemplate.Infrastructure/testTemplate.Infrastructure.csproj reference testTemplate.Domain/testTemplate.Domain.csproj

https://learn.microsoft.com/en-us/dotnet/core/tutorials/cli-templates-create-project-template

mkdir .template.config
create file template.json

==> for dotnet 6 (https://github.com/dotnet/docs/issues/32949)
dotnet new --install ./
or in windows 
dotnet new --install .\

