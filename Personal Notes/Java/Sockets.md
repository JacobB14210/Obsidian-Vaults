# Socket server
```java
import java.io.*;
import java.net.*;

public class SimpleServer {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(5000); // Port 5000
        System.out.println("Server is listening on port 5000...");

        Socket clientSocket = serverSocket.accept(); // Wait for client
        System.out.println("Client connected!");

        OutputStream output = clientSocket.getOutputStream();
        PrintWriter writer = new PrintWriter(output, true);
        writer.println("Hello, Client!");

        clientSocket.close();
        serverSocket.close();
    }
}

```
# Socket client
```java
import java.io.*;
import java.net.*;

public class SimpleClient {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket("localhost", 5000); // Connect to server

        InputStream input = socket.getInputStream();
        BufferedReader reader = new BufferedReader(new InputStreamReader(input));

        String message = reader.readLine();
        System.out.println("Server says: " + message);

        socket.close();
    }
}

```
# PrintWriter and BufferedReader
```java
PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()));
```