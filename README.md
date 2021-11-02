# react-blog

This blog web app demonstrates my ability using the React framework.

**Here is where I will document my efforts in building this ecommerce app.**

I start out by building out the components in the src folder.

The following is a list of the components I'll be building out:

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

_// BlogDetails Component //_

Here is where a single blog post is fetched and displayed.

This component is called by the Link element that includes the blog id in the URL as a param.

Using the getParams() hook, I extract the id and pass it into the useFetch custom hook.

Using the useHistory() hook gives access to a history stack to store visited components and pages.

Here is where the isPending and error data can be utilized as a conditional.

Finally, I put in a delete button with the handleClick function. Which fetches the given blogpost and uses the DELETE method.

Followed by a redirect to the updated Homepage.

_// Create Component //_

This component uses the hooks useState and useHistory.

The useState hook is used to create and set different fields. In this case, a form with fields to fill out and add a blog post.

title, body, author - isPending, history, useHistory

The following functions are used to set the variables dynamically: setTitle, setAuthor, setBody.

The Publish submit button uses the handleSubmit function. But is only displayed if isPending is false. I also make sure to prevent the default refresh behavior.

All the data provided in the form is then made into an object. Then isPending is set to true. The fetch function is also called to use POST method to pass in the blog post.

After successfully being POSTed, isPending is returned to false. And there's a redirect to the updated Home page.

_// useFetch hook //_

The useFetch custom hook fetches the data from our local JSON server.

useState is used to set: data, isPending, error.

Data is set to an empty array.
isPending is set to true.
Error is set to null by default.

Using a local JSON server gives us instant access to our data. However I'm using a setTimeout function to delay fetching.

Once data is fetched, the data is set in the data variable, error set to null, isPending set to false.

The URL is passed in the useEffect hook so whenever the URL is changed, the useEffect hook is called to fetch the data.

The data, isPending, and error is then returned as an object from this function.
