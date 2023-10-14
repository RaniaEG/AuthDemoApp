# AuthDemoApp is a tutorial to show you how to establish the authentication functionality using "Entity Framework" and "AspNetCore Framework".
In Visual Studio, go to:
Create a new project>select "ASP.NET Core Web App (Model-View-Controller)>Click "Next"
Name the App "AuthDemoApp">click "Next"
Make sure the "Framework" is set to ".NET 7.0 (Standard Term Support)"
Set the "Authentication type" to "Individual Accounts" -> this step does it all!
Check the box "Configure for HTTPS"
Then, click "Create"
Then, the magic happens! :)
The App is created with extra things automatically created and installed:
1. The login form, register new user form, forgot password feature, and e-mail confirmation feature are created!
2. The "Data" folder is created, which contains the "Migrations" folder generated by the Entity Framework and "DbContext" class for creating the database and table for manageing users' identity using "AspNetCore" framework
3. The connection string is created in the "appsettings.json":
"ConnectionStrings": {
  "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=aspnet-AuthDemoApp-b1727237-0c1e-4d17-8507-bb3753afc651;Trusted_Connection=True;MultipleActiveResultSets=true"
}
4. The necessary packages for it to work are installed (double-click on the project node in the solution explorer to see them):
 <ItemGroup>
   <PackageReference Include="Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore" Version="7.0.12" />
   <PackageReference Include="Microsoft.AspNetCore.Identity.EntityFrameworkCore" Version="7.0.12" />
   <PackageReference Include="Microsoft.AspNetCore.Identity.UI" Version="7.0.12" />
   <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="7.0.12" />
   <PackageReference Include="Microsoft.EntityFrameworkCore.Tools" Version="7.0.12" />
 </ItemGroup>

Now, go to "Tools" menu in Visual Studio>NuGet Package Manager>Package Manager Console
Then type the two commands:
Add-Migration InitialCreate
Update-Database

To see the database and table created on "MS SQL Server", go to "Tools" menu in Visual Studio and do the following:
Click on "Connect to Server", then ignore the message that asks you to enter the PC name (close it)
Then you will find the "Server Explorer" showed up in a side window; there are 4 icons that appear in that window, click on the icon that when you hover over it, it says "SQL Server Object Explorer"
Then you will find the created database "aspnet-AuthDemoApp-b1727237-0c1e-4d17-8507-bb3753afc651" in the "SQL Server Object Explorer" under SQL Server>(localdb)\MSSQLLocalDB>Databases
Note: you might need to refresh the server many times and close Visual Studio and open it again to see the database in the abovementioned path
Once you find the database, navigate to the "dbo.AspNetUsers" table and double-click on it and check it out!


Now, run the App and try it! you will see "Register" and "Login" links appear on the top-right of the web page!
