# Blog-Website

## Table of contents

- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)

## My process

### Built with

- HTML5
- CSS3
- Bootstrap
- EJS
- MongoDB
- Node.js
- Express.js
- Heroku

### What I learned

I learned how to create and access databases through the creation of this project. I accomplished this by using MongoDB and Mongoose. This was also my first time using EJS in a published website, and I love it for it's ability to create dynamic websites in a very simple to use manner. 

Code written in this project that I want to highlight:

```EJS
<h1>Home</h1>
    <p> <%= startingContent %> </p>


  <%  posts.forEach(function(post){ %>

    <h1><%=post.title%></h1>
    <p>
    <%=post.content.substring(0, 100) + " ..."%>
    <a href="/posts/<%=post._id%>">Read More</a>
    </p>


    <% }) %>
```
This portion of EJS code was used on my home screen to dynamically render the blog posts on the home page as the user creates them. An easy and efficient way to implement JavaScript directly and seamlessly into HTML code.

```Node.js
app.get("/posts/:postId", function(req, res){

const requestedPostId = req.params.postId;

  Post.findOne({_id: requestedPostId}, function(err, post){
    res.render("post", {
      title: post.title,
      content: post.content
    });
  });

});
```
This code, found in my app.js file, creates a parameter from the title of the post the user makes, and creates a link to it on the server.  

### Continued development

EJS is an incredibly powerful and useful tool to use to create synamic websites. I would love to venture further into it to see what else it can acheive. Along with this, in the future, I would loved to create a more visually appealing blog website with pictures displayed in the post along with an upload option so that users can upload their own.

## Author

- Website - [Elyse Chambers](https://www.diaryofelyse.com)
- Frontend Mentor - [Elyseeloo](https://www.frontendmentor.io/profile/Elyseeloo)
- Twitter - [@Elyseeloo\_](https://www.twitter.com/elyseeloo_)
