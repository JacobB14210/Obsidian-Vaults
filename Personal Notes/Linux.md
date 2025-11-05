```clike
// Server related commands

// Run a java server continuously even when terminal is offline
nohup <java file or Gradle command> &
// -& (Run file continuously)

// Check status of port, also gives PID
netstat -tulnp | grep <PORT_NUMBER>
// -t (TCP connections)
// -u (UDP connections)
// -l (Show listening ports)
// -n (Show numerical addresses)
// -p (Show PID and Process name using the PORT_NUMBER)

// Kill process
kill <PID>

// Remove file
rm filename

// Remove Directory
rm -r directoryname
// -r (Deletes directory and everything inside)
```