I can see the issue - Vite is running on `http://localhost:5173/` but Tauri is waiting for the frontend dev server on `http://localhost:8080/`. There's a port mismatch.

Let me check the Tauri configuration file to fix this:

[1 tool called]

Found it! The `devUrl` in the Tauri config is set to port 8080, but Vite is running on port 5173. I'll fix this:

[1 tool called]

Fixed! I've updated the `devUrl` in `src-tauri/tauri.conf.json` from port 8080 to port 5173 to match Vite's default port.

You'll need to restart the Tauri dev process for the change to take effect. Stop the current process (Ctrl+C) and run `npm run tauri dev` again.