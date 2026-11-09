# RaceDay Event Management — Part 3

## Project structure

The solution contains three projects:

- `RaceDay.Api` — ASP.NET Core Web API and Entity Framework Core database access.
- `RaceDay.Web` — ASP.NET Core MVC website. It calls the API using `HttpClient`; it does not connect directly to the database.
- `RaceDay.Api.Tests` — automated API tests.

Open `RACEDAY.sln` from this folder in Visual Studio 2022.



After opening the solution and restoring NuGet packages, opened **Tools → NuGet Package Manager → Package Manager Console**.

Set the Default project to `RaceDay.Api`, then run:

```powershell
Add-Migration AddPart3ImageFields
Update-Database
```

## Implemented MVC features

### Accounts
- Participant and Organiser registration through the API.
- Login and logout through the API.
- MVC session state and role-specific navigation.
- Protected dashboard and feature pages.

### Organiser
- Organiser dashboard.
- Create, list, edit and delete events.
- Upload event banner images.
- Add, edit and delete event categories.
- View enrolments for an event.
- Enter and delete race results.

### Participant
- Participant dashboard.
- Browse and filter events by event name, venue, city and event type.
- View event details and categories.
- Enrol in an event category.
- View own event enrolments and status.
- View own results, event date, category, finish time and positions.
- View and update participant profile.

## Image storage

Profile pictures and event banners are uploaded by the MVC website into its `wwwroot` folder:

- Profile pictures: `RaceDay.Web/wwwroot/images/profiles`
- Event banners: `RaceDay.Web/wwwroot/images/events`

The relative image path is saved through the API in the database and used to display the image. Image uploads are limited by file extension and size. This implementation uses local `wwwroot` storage, not Azure Blob Storage, following the lecturer's instruction shared for this project.

The files are stored on the web server. For deployment to multiple web servers or ephemeral hosting, a shared persistent file store would be needed.

## Submission checklist

- Push the full `RaceDayPart2` repository folder, including `RaceDay.Web`, to GitHub.
- Make regular, meaningful commits while completing and testing each feature.
- Confirm GitHub Actions passes.
- Update this README with the final run instructions and any lecturer-specific changes.
- Record the required unlisted demonstration video and add its link here.
- added unlisted youtube video
  
