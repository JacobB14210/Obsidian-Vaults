```jsx
import { useEffect, useState } from "react";

function App() {
	const [username, setUsername] = useState(null); // Set variable

    useEffect(() => { // Run after
        fetch("http://localhost:5000/username?username=Jacob")
            .then(response => response.json())
            .then(data => setUsername(data));
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