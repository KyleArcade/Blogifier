
### First-run setup
On a fresh installation, the home page redirects to `/account/initialize`. Use this page to set the blog title and description and create the first account. That account is assigned the Administrator role; there are no default admin credentials.

After setup, sign in at `/account/login` and open the admin application at `/admin`.

### Authentication
The blog posts, including blog themes, are all run as public, server-side rendered MVC site. 

Anything under `admin` is Blazor Web Assembly application and is guarded by custom authentication provider (`BlogAuthenticationStateProvider`). 
User passwords are hashed by ASP.NET Core Identity and saved in the `Authors` table on the back-end.

The `Blogifier:Salt` setting in `src/Blogifier/appsettings.json` is not currently used by the password-hashing code. Changing it does not change how account passwords are hashed.