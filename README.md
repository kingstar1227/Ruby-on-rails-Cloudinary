# ArtBook

[![tested with jest](https://img.shields.io/badge/tested_with-jest-99424f.svg)](https://github.com/facebook/jest)
[![tested with rspec](https://img.shields.io/badge/tested%20with-rspec-brightgreen.svg)](https://github.com/rspec/rspec-rails)

https://artbookapp.herokuapp.com/

ArtBook is a portfolio showcase web application. It is a full-stack app built using a Ruby on Rails backend, Postgresql database, and React/Redux front-end architecture.

## Planning & Design

[Design documents can be found in the wiki!](https://github.com/anastassia-b/art-book-app/wiki)

## Features & Implementation

### Secure Authentication
* BCrypt for password-salting and hashing for a secure authentication system.
* Guest / Demo Account

![Session](http://g.recordit.co/DTgAZHML7h.gif)

### Modals

Modals were used to implement the Login/Signup session forms, as well as project views.

```javascript
render() {
  const project = this.props.project;
  return (
    <div>
      <div className="project" key={project.id}>
        <section onClick={this.openModal.bind(this)}>
          <img className="thumbnail" src={project.thumbnail_url}/>
        </section>
        <section className="thumbnail-info">
          <span className="project-title">{project.title}</span>
          <Link to={`/users/${project.user_id}`}
                className="artist-name">{project.user}
          </Link>
        </section>
      </div>

      <Modal
        contentLabel="Modal"
        isOpen={this.state.modalOpen}
        onRequestClose={this.closeModal}
        style={style}>

        <div className="x-button">
          <button onClick={this.closeModal}><i aria-hidden="true"></i>
          </button>
        </div>
        <div className="project-detail">
          <ImageIndexContainer project={project}/>
          <ProjectInfoContainer project={project}/>
        </div>
      </Modal>
    </div>
  );
}
```

### Comments and Likes

![Comments and Likes](http://g.recordit.co/aHuEZPU54l.gif)

## Technologies

### Backend
* Ruby On Rails
* jBuilder
* PostgreSQL RDBMS
* Heroku

### Frontend
* React/Redux
* JavaScript
* SCSS/CSS
* npm
* Webpack

### Storage
* Cloudinary for users' profile pictures and project images storage.


## Future Features

### Infinite scroll

This will allow users to keep scrolling to retrieve more content.

### Follows and User-specific Feed

Users will be able to follow each other, allowing for a customizable feed per user.

### Search by content (tags)

Categorizing projects will allow users to search and filter through projects.

### Upload projects

Users will be able to upload, edit, and destroy their own projects through the API.
