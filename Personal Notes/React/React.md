```jsx
import { useEffect, useState } from "react";

function App() {
    const [users, setUsers] = useState([]); // Set variable and function

    useEffect(() => {
        fetch("http://localhost:5000/users") // sends a fetch for users
            .then(response => response.json())
            .then(data => setUsers(data));
    }, []);

    return (
        <div>
            <h1>Users</h1>
            {users.map(user => (
                <div key={user.id}>
                    {user.username} - {user.email}
                </div>
            ))}
        </div>
    );
}

export default App
```