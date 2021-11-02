# react-blog

This blog web app demonstrates my ability using the React framework.

**Here is where I will document my efforts in building this ecommerce app.**

I start out by building out the components in the src folder.

The following is a list of the components I'll be building:

**App.js** will use BrowserRouter to link all the pages and give them paths and components to load within the page.

**Home.js** is the homepage of the blog. The blog posts will be in list format, not with logic but instead by calling the BlogList component to pass each post to display in a list. This component will use a custom hook to fetch the posts/

**BlogList.js** recieves the blog posts for to display in a list format.

**BlogDetails.js** fetches a single blog post to view on its own page.

**Create.js** is to create new blog posts and add them to the list.

**Navbar.js** for navigation.

**NotFound.js** is an error page.

**UseFetch.js** is a custom hook used to fetch data from the local JSON server I'm utilizing.

To start, I create each of these files in my project. Now I'll start building out each one:

_// Home Component //_

I start by importing the Bloglist component and useFetch (which I'll be building later).

The useFetch custom hook takes in a URL that gives the following data:

- blogs, which is the blog data
- isPending, which lets us know data is being fetched
- error, which means there's an issue

This data will be used to determine what to display.

Then I have the blogs and title passed into the BlogList component to display a list.

_// BlogList Component //_

The blog posts and blog titles passed in from the Home component are displayed via this component.

Utilizing Link from react-router-dom lets me link text and images to a URL, with no need to refresh between pages. This quick access to locally saved data, as opposed to calling the server, is what makes this a snappy React single page app.

Now I iterate over the blog posts. This means I map _blogs_ and for every _single_ blog post, the process is repeated per each blog post id.

Then I make sure to use the id to link to the blog post's respective page.
