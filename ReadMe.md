*Files to look at*:

- [Index.cshtml](./CS/SaveDashboardDB/Views/Home/Index.cshtml)
- [DataBaseEditaleDashboardStorage.cs](./CS/SaveDashboardDB/Code/DataBaseEditaleDashboardStorage.cs)
- [Startup.cs](./CS/SaveDashboardDB/Startup.cs#L30)

# Dashboard for ASP.NET Core - How to load and save dashboards from/to a database

This example shows how to create custom dashboard storage in an ASP.NET Core application and to store dashboards in a database.
To create custom dashboard storage, implement <strong>IDashboardStorage</strong> or <strong>IEditableDashboardStorage</strong>.

<strong>IDashboardStorage</strong> allows you to open and edit dashboards from storage.

<strong>XDocument LoadDashboard(string dashboardID) </strong> - returns a dashboard by its ID in XDocument format.

<strong>IEnumerable<DashboardInfo> GetAvailableDashboardsInfo()</strong> - returns a list of dashboard IDs and Captions from data storage.

<strong>void SaveDashboard(string dashboardID, XDocument dashboard)</strong> - updates the dashboard with new settings by the dashboard's id.


<strong>IEditableDashboardStorage</strong> inherits the <strong>IDashboardStorage</strong> interface and contains an extra method that adds new dashboards to storage.

<strong>string AddDashboard(XDocument dashboard, string dashboardName)</strong> - obtains a dashboard definition with its caption, saves it to the data storage, and returns the ID of the newly saved dashboard.


This example also contains an SQL file ([SavedDashboards.sql](./CS/SaveDashboardDB/SavedDashboards.sql)). You can use it to recreate a database on your side. Do not forget to update the connection string in the <strong>appsettings.json</strong> file to make it valid in your environment.

## Documentation
- [IDashboardStorage](https://docs.devexpress.com/Dashboard/DevExpress.DashboardWeb.IDashboardStorage)
- [IEditableDashboardStorage](https://docs.devexpress.com/Dashboard/DevExpress.DashboardWeb.IEditableDashboardStorage)

## More Examples

- <a href="https://www.devexpress.com/Support/Center/p/T392813">How to save dashboards created in ASPxDashboard to a DataSet</a>
- <a href="https://www.devexpress.com/Support/Center/p/T400693">MVCxDashboard - How to save dashboards to a database</a>
- <a href="https://www.devexpress.com/Support/Center/p/T954359">MVC Dashboard - How to implement multi-tenant Dashboard architecture</a>
