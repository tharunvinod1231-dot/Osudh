
# Replit Bedrock Keep-Alive Bot

This repo runs a Bedrock AFK / keep-alive bot on Replit.

Defaults:
- Host: Tvin.aternos.me
- Port: 60815
- Username: shuppandi
- Offline mode: true
- Background mode: true

Override with Replit Secrets (environment variables).


After adding files, click the big Run button. Replit should install dependencies automatically. If it doesn't, open Shell and run:

npm install

Add Replit Secrets (environment variables)

Click the lock icon (Secrets) in the left panel and add each of the following:

MC_HOST = Tvin.aternos.me

MC_PORT = 60815

MC_USER = shuppandi

MC_OFFLINE = true

BACKGROUND_MODE = true

ACTIVITY_MS = 30000

RECONNECT_MS = 5000

PORT = 5000

(Click Add Secret after typing each key/value.)

Start & verify

Click Run.

Console should show:

HTTP endpoint listening on port 5000 (hit / to wake repl)

Starting Bedrock client -> Tvin.aternos.me:60815 username=shuppandi offline=true (or similar)

When joined: Joined server. Starting anti-AFK activity. (if BACKGROUND_MODE=false you'll see logs)

If you do not see these, copy any console errors and paste them here and I'll tell you exactly what to change.

Keep the Repl awake 24x7 (choose one)

Replit Always-On (paid) - enable Always-On in Repl settings (best).

UptimeRobot (free) - create an UptimeRobot monitor that pings your Repl URL every 5 minutes:

URL: https://<your-repl-name>.<your-username>.repl.co/ (use the Open button in Replit to get the exact URL)

Monitor type: HTTP(s), interval 5 minutes

The bot exposes / and /status.

Troubleshooting common issues

Package install fails: open Shell and run npm install and paste the error here.

Immediately kicked / protocol errors: add a version option to bedrock.createClient({ ... , version: '1.21.124' }) in index.js, save, and re-run. If that still errors, paste the exact console error.

Bot not visible in server: confirm server IP and port are correct, and that the server allows offline players (MC_OFFLINE=true). If server requires Xbox auth, set MC_OFFLINE=false and tell me and I'll walk you through auth (more steps).
