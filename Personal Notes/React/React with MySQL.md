```jsx
import { useEffect, useState } from "react";

function App() {
	const [username, setUsername] = useState(null); // Set variable

    useEffect(() => { // Run after
        fetch("http://localhost:5000/username?username=Jacob") // Fetch API request
            .then(response => response.json()) // Get the response
            .then(data => setUsername(data)); // Set the variable
    }, []);

    return (
        <div>
            {email && (
                <div>
                    {email.username} - {email.email}
                </div>
            )}
        </div>
    );
}

export default App
```