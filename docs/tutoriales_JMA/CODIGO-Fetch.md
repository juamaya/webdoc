# Fetch 

## Usando APis

## Apis.jsx

```jsx

import React, { useEffect, useState } from 'react'
import PostCard from '../components/PostCard'
import UserCard from '../components/UserCard'

const Apis = () => {

  const [posts, setPosts] = useState([])
  const [users, setUsers] = useState([])

  const [errorP, setErrorP] = useState(false)
  const [errorU, setErrorU] = useState(false)


  const getPosts = async () => {

    try {
      const res = await fetch("https://jsonplaceholder.typicode.com/posts")
      const data = await res.json()
      console.log(data)
      setPosts(data)
      setErrorP(false)
    } catch (e) {
      setErrorP(true)
      console.log(e)
    }
  }

  const getUsers = async () => {
    try {
      const res = await fetch("https://jsonplaceholder.typicode.com/users")
      const data = await res.json()
      console.log(data)
      setUsers(data)
      setErrorU(false)
    } catch (e) {
      setErrorU(true)
      console.log(e)
    }
  }

  useEffect(() => {
    getPosts()
    getUsers()
  }, [])


  const userCards = users.map((user) => {
    return (
      <li key={user.id}>
        <UserCard user={user} />
      </li>
    )
  })

  const postCards = posts.map((post) => {
    return (
      <li key={post.id}>
        <PostCard post={post} />
      </li>
    )
  })


  return (
    <>
      <div>Apis</div>
      <h3>Traemos Datos de la Api:  "https://jsonplaceholder.typicode.com/users" </h3>
      <h2>Users</h2>
      <section>

        <ul>{userCards}</ul>
      </section>

      <h3>Traemos Datos de la Api:  "https://jsonplaceholder.typicode.com/posts" </h3>
      <h2>Posts</h2>
      <section>

        <ul>{postCards}</ul>
      </section>
    </>
  )

}
export default Apis
```

## PostCard.jsx

```jsx

const PostCard = (props) => {

    const { post } = props


    return (
        <>
            <h2>{post.id} : {post.title}</h2>
            <p>{post.body}</p>
        </>
    )
}

export default PostCard

```


## UserCard.jsx

```jsx

const UserCard = (props) => {

    const { user } = props
    return (
        <>
            <h2>{user.id} : {user.name}</h2>
            <h4>Email: {user.email}</h4>
        </>
    )
}

export default UserCard


```