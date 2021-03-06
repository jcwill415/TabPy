# TabPy Security Considerations

If security is a significant concern within your organization,
you may want to consider the following as you use TabPy:

- The REST server and Python execution share the same Python session,
  meaning that HTTP requests and user scripts are evaluated in the
  same addressable memory and processor threads.
- The tabpy_tools client does not perform client-side validation of the
  SSL certificate on TabPy Server.
- Python scripts can contain code which can harm security on the server
  where the TabPy is running. For example, Python scripts can:
  - Access the file system (read/write).
  - Install new Python packages which can contain binary code.
  - Execute operating system commands.
  - Open network connections to other servers and download files.
