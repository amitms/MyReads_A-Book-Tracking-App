MyReads: A Book Tracking App
===

This Project is React front-end code to search for books and catalogue them in different shelves.
Back-end API and data storage is provided by Udacity. This project is part of Udacity React Nanodegree Program.

### App info
The main page contains a list of books catalogued by shelf. Available shelves are: currently reading, want to read and read.
It is possibile to move a book from a shelf to another, by using the dropdown provided on bottom-right corner of each book.
To completely remove a book from these shelves choose shelf -> None.

![Main page](/myreadssnapshots.JPG)

By clicking on the page bottom-right plus icon user gets redirected to `/search` URL.
Here it is possibile to search for books by typing a keyword.
Search is gonna call a backend server and return a maximum of 20 results.

>Due to the exercise nature of the project, the backend API uses a fixed set of cached search results and is limited to a particular set of search terms, which can be found in [SEARCH_TERMS.md](SEARCH_TERMS.md). That list of terms are the _only_ terms that will work with the backend.

Once search results are displayed it is possibile to move a book to a shelf by using the same dropdown functionality described for main page. Books that already belong to a shelf are displayed accordingly.

### Setup
- download or clone the project folder (master branch)
- open your terminal and navigate to project folder
- make sure you have Node.js and npm installed, or get them [here](https://nodejs.org/it/download)
- run `npm install` or `yarn install` to install all required dependencies
- run `npm start` or `yarn start`

A browser window with the working app should open http://localhost:3000/

## Backend Server

To simplify your development process, we've provided a backend server for you to develop against. The provided file [`BooksAPI.js`](src/Utils/BooksAPI.js) contains the methods you will need to perform necessary operations on the backend:

### `getAll()`
* Returns a Promise which resolves to a JSON object containing a collection of book objects.
* This collection represents the books currently in the bookshelves in your app.

### `update(book, shelf)`
* book: `<Object>` containing at minimum an `id` attribute
* shelf: `<String>` contains one of ["wantToRead", "currentlyReading", "read"]  
* Returns a Promise which resolves to a JSON object containing the response data of the POST request

### `search(query, maxResults)`
* query: `<String>`
* maxResults: `<Integer>` Due to the nature of the backend server, search results are capped at 20, even if this is set higher.
* Returns a Promise which resolves to a JSON object containing a collection of book objects.
* These books do not know which shelf they are on. They are raw results only. You'll need to make sure that books have the correct state while on the search page.
