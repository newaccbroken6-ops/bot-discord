# Free Fire Bio Update Discord Bot

This Discord bot allows users to update Free Fire bios using the Flexbase-Long-Bio-Api.

## Prerequisites

- Python 3.8 or higher
- A Discord bot token from the [Discord Developer Portal](https://discord.com/developers/applications)
- Access to the Free Fire API server

## Installation & Local Setup

1. Install the required packages:
```bash
pip install -r requirements.txt
```

2. Configure environment variables:
   - Create a `.env` file in the root directory with the following content:
   ```
   DISCORD_BOT_TOKEN=YOUR_VALID_DISCORD_BOT_TOKEN_HERE
   API_BASE_URL=https://long-bio-dusky.vercel.app/
   ```
   - Get a Discord bot token:
     1. Go to https://discord.com/developers/applications
     2. Create a new application
     3. Create a bot under the application
     4. Copy the token from the "Token" section
     5. Add the bot to your server using the OAuth2 URL generator

## Hosting Options

### Option 1: Render (Recommended)

The bot is already configured for deployment on Render using the `render.yaml` file.

1. Push your code to a GitHub repository
2. Connect your repository to Render
3. Add your environment variables in the Render dashboard:
   - DISCORD_BOT_TOKEN
   - API_BASE_URL
4. Deploy and your bot will be running automatically

### Option 2: Vercel (Alternative)

The bot can also be deployed on Vercel using the `vercel.json` file.

1. Install the Vercel CLI:
```bash
npm install -g vercel
```

2. Deploy to Vercel:
```bash
vercel --prod
```

3. Set environment variables in the Vercel dashboard:
   - DISCORD_BOT_TOKEN
   - API_BASE_URL

### Option 3: Other Cloud Platforms (Heroku, DigitalOcean, etc.)

1. Clone your repository to the platform
2. Set the environment variables:
   - DISCORD_BOT_TOKEN
   - API_BASE_URL
3. Specify the runtime version (Python 3.11) if required
4. Run the start command: `python bot.py`

## Usage

Run the bot:
```bash
python bot.py
```

```
!bio <uid> <password> <bio_text>` - Updates the Free Fire bio using UID and password
!bio_jwt <jwt_token> <bio_text>` - Updates the Free Fire bio using JWT token
!bio_access <access_token> <bio_text>` - Updates the Free Fire bio using access token
!help_ff` - Shows help information

```
!bio 1234567890 mypassword123 This is my new bio!
!bio_jwt eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9... My JWT bio!
!bio_access access_token123 Another bio!
```

### Commands

- `!bio <uid> <password> <bio_text>` - Updates the Free Fire bio using UID and password
- `!bio_jwt <jwt_token> <bio_text>` - Updates the Free Fire bio using JWT token
- `!bio_access <access_token> <bio_text>` - Updates the Free Fire bio using access token
- `!help_ff` - Shows help information

### Examples

```
!bio 1234567890 mypassword123 This is my new bio!
!bio_jwt eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9... My JWT bio!
!bio_access access_token123 Another bio!
```

## Important Security Notice

- Keep your Discord bot token secure
- Never share account credentials in public channels
- The bot transmits account information to update the bio, so only use in private channels if possible