<script>
  import { Router, Route, Link } from 'svelte-navigator';
  import UserDetail from './UserDetail.svelte';

  import Users from './Users.svelte';
</script>

<Router>
  <header>
    <nav>
      <Link to="/">Home</Link>
      <Link to="about">About</Link>
      <Link to="users">Users</Link>
    </nav>
  </header>
  <main>
    <Route path="/">
      <h1>This is the Home page</h1>
    </Route>
    <Route path="users">
      <Users />
    </Route>
    <Route path="user/:userId" component={UserDetail} />

    <Route path="about">
      <h1>This is the about page</h1>
    </Route>
  </main>
</Router>
