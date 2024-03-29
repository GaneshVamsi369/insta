In this project let's build a **Instgram Clone App**.


<details>
<summary>Project Description</summary>

Implemented responsive Instagram Clone where users can see the user stories, posts, user profile and the my profile section where the user can interact with the posts and stories like Instagram. Users can see the posts, user stories of the different users.

- Implemented different routes for features like home, specific user profile page, specific my profile page using React Router components Route, Switch, Link.
- Implemented Authentication by the user credentials and generated a token on succssful authentication.
- Implemented protected route to ensure only authenticated users are able to access the pages like users, user profile, search, profile sections.

Technologies used: HTML, CSS, JavaScript, React JS, Rest API Calls, React Slick.

</details>

### Set Up Instructions

<details>

<summary>Click to view</summary>

- Download dependencies by running `npm install`

- Start up the app using `npm start`

</details>

### Completion Instructions

<details>
<summary>Functionality to be added</summary>
<br />
The app must have the following functionalities

- **Login Route**

  - When an invalid username and password are provided and the Login button is clicked, then the respective error message received from the response should be displayed
  - When a valid username and password are provided and the Login button is clicked, then the page should be navigated to the Home Route
  - When an _unauthenticated_ user tries to access the Home Route, Profile Route, and User Profile Route, then the page should be navigated to the Login Route
  - When an _authenticated_ user tries to access the Home Route, Profile Route, and User Profile Route, then the page should be navigated to the respective route
  - When an _authenticated_ user tries to access the Login Route, then the page should be navigated to the Home Route

- **Home Route**

  - When an _authenticated_ user opens the Home Route

    - An HTTP GET request should be made to **User Stories API URL** with `jwt_token` in the Cookies

      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the failure view given in the **Figma** screens should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **User Stories API URL**

    - An HTTP GET request should be made to the **Posts API URL** with `jwt_token` in the Cookies

      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the failure view given in the **Figma** screens should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **Posts API URL**

    - Initially for every Post **BsHeart**, **FaRegComment**, **BiShareAlt** from `react-icons` should be displayed
    - When the **username** in the particular post is clicked, then the page should be navigated to the User Details Route
    - When the **Like** icon (FcLike) is clicked,
      - An HTTP POST request should be made to the **Post Like API URL** with `like_status` as `true`
      - It should change to **Unlike** icon (BsHeart)
      - Likes count of that particular post should be incremented by one
    - When the **Unlike** icon is clicked,

      - An HTTP POST request should be made to the **Post Like API URL** with `like_status` as `false`
      - It should change to **Like** icon
      - Likes count of that particular post should be decremented by one

    - **Header**

      - When the Website logo is clicked, then the page should be navigated to the Home Route
      - When the **Home** link in the Header is clicked, then the page should be navigated to the Home Route
      - When the **Profile** link in the Header is clicked, then the page should be navigated to the My Profile Route
      - When the **Logout** button is clicked, then the page should be navigated to the Login Route

- **User Profile Route**

  - When an _authenticated_ user opens the User Profile Route

    - An HTTP GET request should be made to the **User Profile API URL** with `jwt_token` in the Cookies and `user_id` as a path parameter

      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the failure view given in the **Figma** screens should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **User Profile API URL**

    - The list of posts section should contain the **BsGrid3X3** from `react-icons`
    - If the list of posts are empty, then the No Posts View in the **Figma** screens should be displayed
    - If the list of posts are empty, then the **BiCamera** from `react-icons` should be displayed
    - All the header functionalities mentioned in the Home Route should work in this route accordingly

- **My Profile Route**

  - When an _authenticated_ user opens the My Profile Route

    - An HTTP GET request should be made to the **My Profile API URL** with `jwt_token` in the Cookies

      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the failure view given in the **Figma** screens should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **My Profile API URL**

    - The list of posts section should contain the **BsGrid3X3** from `react-icons`

- **Search Functionality**

  - When an _authenticated_ user search posts using **post caption** by clicking on the Search icon (`FaSearch` from `react-icons`)

    - An HTTP GET request should be made to the **Search Posts API URL** with `jwt_token` in the Cookies and search post as a query parameter

      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the failure view given in the **Figma** screens should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **Search Posts API URL**

    - If the search posts are empty, then the Search Not Found View in the **Figma** screens should be displayed
    - Initially for every Post **BsHeart**, **FaRegComment**, **BiShareAlt** from `react-icons` should be displayed
    - When the **username** in the particular post is clicked, then the page should be navigated to the User Details Route
    - When the **Like** icon is clicked,
      - An HTTP POST request should be made to the **Post Like API URL** with `like_status` as `true`
      - It should change to **Unlike** icon
      - Likes count of that particular post should be incremented by one
    - When the **Unlike** icon is clicked,
      - An HTTP POST request should be made to the **Post Like API URL** with `like_status` as `false`
      - It should change to **Like** icon
      - Likes count of that particular post should be decremented by one

- **Not Found Route**

  - When a random path is provided in the URL, then the page should be navigated to the Not Found Route

- Users should be able to view the website responsively in mobile view, tablet view as well

</details>


### Important Note

- In this project, the data you have sent through `POST-APIs` are not saved in the `Database`. If you refresh the page, the changes will not be persisted
- Whenever you do a `POST-API` call, we are sending a mock object as a response



### Resources

<details>
<summary>Data fetch URLs</summary>

- **Note**: Use the values in the APIs as shown below

- Use the search input value in place of `searchInput` in the query parameters
- The value of the key `user_id` should be given in the place of `userId`

- **Note:** Use the below sample code snippet to make a POST request on Login using valid username and password.

  ```js
  const options = {
    method: 'POST',
    body: JSON.stringify(userDetails),
  }
  ```

**Login API**

#### API: `https://apis.ccbp.in/login`

#### Method: `POST`

#### Description:

Returns a response based on the credentials provided

#### Sample request object:

```json
{
  "username": "rahul",
  "password": "rahul@2021"
}
```

#### Sample Success Response

```json
{
  "jwt_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InJhaHVsIiwicm9sZSI6IlBSSU1FX1VTRVIiLCJpYXQiOjE2MTk2Mjg2MTN9. nZDlFsnSWArLKKeF0QbmdVfLgzUbx1BGJsqa2kc_21Y"
}
```

#### Sample Failure Response

```json
{
  "status_code": 404,
  "error_msg": "Username is not found"
}
```

**User Stories API**

#### API: `https://apis.ccbp.in/insta-share/stories`

#### Method: `GET`

#### Description:

Returns a response containing the list of all user stories

#### Sample Response

```json
{
  "users_stories": [
    {
      "user_id": "Varun_Aadithya",
      "user_name": "Varun Aadithya",
      "story_url": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/stories/instagram-mini-project-story-1-img.png"
    },
    ...
  ],
  "total": 9
}
```

**Posts API**

#### API: `https://apis.ccbp.in/insta-share/posts`

#### Method: `GET`

#### Description:

Returns a response containing the list of user posts.

#### Sample Response

```json
{
  "posts": [
      {
      "post_id": "f25d77f0-602e-41d1-971e-4b8cf54709eb",
      "user_id": "Varun_Aadithya",
      "user_name": "Varun Aadithya",
      "profile_pic": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/users/instagram-mini-project-user-1-img.png",
      "post_details": {
  	    "image_url": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/posts/instagram-mini-project-post-1-img.png",
  	    "caption": "Another day, another sunrise"
      },
      "likes_count": 7,
      "comments": [{
          "user_name": "Prabuddha Dasgupta",
          "user_id": "Prabuddha_Dasgupta",
          "comment": "Lightning is incredible."
      },
      ...
      ],
      "created_at": "4 Hours Ago"
  },
  ...
  ],
  "total": 33
}
```

**Post Like API**

#### API: `https://apis.ccbp.in/insta-share/posts/{postId}/like`

#### Example: `https://apis.ccbp.in/insta-share/posts/f25d77f0-602e-41d1-971e-4b8cf54709eb/like`

#### Method: `POST`

#### Request:

```json
{
  "like_status": true // If you want to like a post then set like_status as true otherwise set it as false.
}
```

#### Description:

Returns a response containing the whether post has been liked or not

#### Sample Response

```json
{
  "message": "Post has been liked"
}
```

**My Profile API**

#### API: `https://apis.ccbp.in/insta-share/my-profile`

#### Method: `GET`

#### Description:

Returns a response containing the details of my profile

#### Sample Response

```json
{
    "profile": {
        "id": "df3234jkjn2-324sdf1132nnknn-234324234",
        "user_id": "rahul",
        "user_name": "Rahul",
        "profile_pic": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/profile/instagram-mini-project-profile-1.png",
        "followers_count": 289,
        "following_count": 12,
        "user_bio": "It is not the strongest of the species that survive, nor the most intelligent, but the one most responsive to change.",
        "posts": [
            {
                "id": "1a698dc4-sdf6e83-4ede-998e-638305f7aee6",
                "image": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/posts/instagram-mini-project-post-31-img.png"
            },
        ...
        ],
        "posts_count": 3,
        "stories": [
            {
                "id": "5HJ25nUNJ",
                "image": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/previous-stories/instagram-mini-project-previous-story-34-img.png"
            },
        ...
        ]
    }
 }
```

**User Profile API**

#### API: `https://apis.ccbp.in/insta-share/users/{userId}`

#### Example: `https://apis.ccbp.in/insta-share/users/Prabuddha_Dasgupta`

#### Method: `GET`

#### Description:

Returns a response containing the details of user profile.

#### Sample Response

```json
{
    "user_details": {
    	"id": "df3234jkjn2-32432nnknn-w23231",
        "user_id": "Prabuddha_Dasgupta",
        "user_name": "Prabuddha Dasgupta",
        "profile_pic": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/users/instagram-mini-project-user-4-img.png",
        "followers_count": 297,
        "following_count": 303,
        "user_bio": "Prabuddha Dasgupta (21 September 1956 – 12 August 2012) was an Indian fashion and fine-art photographer. ",
        "posts_count": 3,
        "posts": [
            {
                "id": "390562f5-298f-4904-aea4-07ecc212febe",
                "image": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/posts/instagram-mini-project-post-10-img.png"
            },
        ...
        ],
        "stories": [
            {
                "id": "UnrObltRP",
                "image": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/previous-stories/instagram-mini-project-previous-story-10-img.png"
            },
        ...
        ]
    }
}
```

**Search Posts API**

#### API: `https://apis.ccbp.in/insta-share/posts?search={searchInput}`

#### Example: `https://apis.ccbp.in/insta-share/posts?search=sky`

#### Method: `GET`

#### Description:

Returns a response containing the list of search posts.

#### Sample Response

```json
{
  "posts": [
      {
        "post_id": "6fb210a9-0c4d-431f-8585-b3a4f065a171",
        "user_id": "Atul_Kasbekar",
        "user_name": "Atul Kasbekar",
        "profile_pic": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/users/instagram-mini-project-user-5-img.png",
        "post_details": {
            "image_url": "https://assets.ccbp.in/frontend/react-js/instagram-mini-project/posts/instagram-mini-project-post-5-img.png",
            "caption": "The sky is the daily bread of the eyes."
        },
        "likes_count": 9,
        "comments": [
            {
                "user_name": "Arjun Mark",
                "user_id": "Arjun_Mark",
                "comment": "Aim for the sky, but move slowly, enjoying every step along the way."
            },
        ...
        ],
        "created_at": "4 Hours Ago"
        },
    ...
    ],
  "total": 2
}
```

</details>

### User Credentials

<details>
<summary>Click to view user credentials</summary>

<br/>

**You can use any one of the following credentials**

```text
  username: aakash
  password: sky@007
```

```text
  username: agastya
  password: myth#789
```

```text
  username: advika
  password: world@5
```

```text
  username: binita
  password: modest*6
```

```text
  username: chetan
  password: vigor$life
```

```text
  username: deepak
  password: lightstar@1
```

```text
  username: harshad
  password: joy@85
```

```text
  username: kapil
  password: moon$008
```

```text
 username: rahul
 password: rahul@2021
```

```text
  username: shravya
  password: musical#stone
```

```text
  username: lucifer
  password: lucifer
```

<br/>
</details>
