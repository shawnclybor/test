# MCP Overview

## GitHub MCP Server Summary

The GitHub MCP (Model Context Protocol) server is a background process that enables me to interact with the GitHub API. Here’s a brief overview of how it works:

*   **Execution**: The server typically runs inside a Docker container, which is launched automatically by your development environment when needed. This ensures a consistent and isolated environment for the server to operate in.
*   **Configuration**: The server is configured in a dedicated settings file (`cline_mcp_settings.json` in this case). This file specifies the command to run the server and provides necessary environment variables.
*   **Tool Availability**: Once the server is running and authenticated, it exposes a set of tools that I can use to perform various GitHub operations, such as creating repositories, managing issues, and interacting with pull requests.

## Supabase MCP Server Summary

The Supabase MCP server provides a direct connection to your Supabase projects, allowing me to interact with your database and other Supabase services. Here’s how it’s set up:

*   **Execution**: Instead of a local installation, the server is run on-demand using `npx`. This command fetches and executes the latest version of the server from the npm registry, ensuring you're always up-to-date.
*   **Configuration**: The server is configured in `cline_mcp_settings.json`. This entry specifies the `npx` command, the project reference to scope the connection, and the `SUPABASE_ACCESS_TOKEN` for authentication.
*   **Tool Availability**: Once active, the server provides a powerful set of tools for database management. This includes listing tables, executing SQL queries, applying migrations, and leveraging advanced features like semantic search with `pg_vector`.

## Filesystem MCP Server Summary

The Filesystem MCP server grants me direct access to your local file system, allowing for a wide range of file and directory operations. Here’s how it’s configured:

*   **Execution**: The server is run on-demand using `npx`, which fetches and executes the `@modelcontextprotocol/server-filesystem` package.
*   **Configuration**: In `cline_mcp_settings.json`, the server is configured with the `npx` command. Crucially, the `args` array specifies which local directories I am allowed to access. This acts as a security sandbox, limiting my operations to only the paths you explicitly grant.
*   **Tool Availability**: With the server active, I can perform essential filesystem tasks, including reading and writing files, creating and listing directories, moving files, and searching for files within the allowed directories.
