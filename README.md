# ZAIRoleBasedHelper
ZAIRoleBasedHelper is a powerful Discord bot cog that brings multiple AI personalities (personas) to your server, powered by Google's Gemini AI. Each persona can be customized with unique behaviors, expertise areas, and access restrictions, allowing you to create a rich, interactive AI ecosystem tailored to your community's needs.


> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)


# ZAI Role-Based Helper

## Overview

ZAI Role-Based Helper is a sophisticated Discord bot that brings customizable AI personas to your server. Each persona is powered by Google's Gemini AI and can be configured with unique personalities, expertise areas, response styles, and access restrictions. This bot enables server administrators to create specialized AI assistants tailored to different topics, roles, and use cases.

## Key Features

### 🎭 Multi-Persona System
- Create unlimited AI personas with distinct personalities and expertise
- Each persona has its own system prompt, description, and behavior
- Personas can redirect users to more appropriate personas when questions don't match their expertise
- Smart persona suggestion system based on question content
- Usage statistics tracking for each persona

### 🔒 Advanced Security & Permissions
- API keys encrypted using AES-256 encryption (guild-specific)
- Manager role system for delegated administration
- Required role enforcement per persona
- Administrator override for all permissions
- Secure credential storage

### 🎯 Granular Access Control
- Channel restrictions per persona
- Role-based rate limiting
- Required roles for specific personas
- Default rate limits for all users
- Custom rate limits per role

### 📊 Rate Limiting & Cooldowns
- Daily and weekly usage limits
- Per-persona cooldown timers
- Role-specific rate limit overrides
- Automatic reset timers
- Real-time usage tracking

### ⚙️ Customizable Configuration
- Response token limits per persona
- Adjustable cooldown periods
- Model selection (Gemini variants)
- Global default settings
- Smart suggestion toggle

### 📈 Analytics & Monitoring
- Total usage statistics per persona
- Top performer tracking
- Export functionality for data analysis
- Real-time usage updates
- Historical data preservation

---

## Installation & Setup

### Prerequisites
1. A Discord server where you have Administrator permissions
2. A Google Gemini API key (obtain from [Google AI Studio](https://makersuite.google.com/app/apikey))
3. Developer Mode enabled in Discord (User Settings > Advanced > Developer Mode)

### Initial Configuration

#### Step 1: Invite the Bot
Invite the bot to your server using the provided invite link with the following permissions:
- Read Messages/View Channels
- Send Messages
- Embed Links
- Use Slash Commands
- Manage Roles (for permission checking)

#### Step 2: Quick Setup
Once the bot is in your server, use the `/adminpanel` command to access the Quick Setup wizard:

1. Navigate to **Settings** tab
2. Click **🔑 Set API Key**
3. Enter your Gemini API key
4. The bot will validate and encrypt your key
5. Return to the main panel

#### Step 3: Create Your First Persona
1. Open `/adminpanel`
2. Navigate to the **Personas** tab
3. Click **➕ Create New Persona**
4. Fill in the modal:
   - **Persona Name**: A unique identifier (e.g., "TechExpert")
   - **Description**: Brief explanation of the persona's purpose
   - **System Prompt**: Define the AI's behavior, expertise, and personality
   - **Response Length Limit**: Maximum tokens (default: 500)
   - **Required Role ID**: Optional role requirement

---

## User Commands

### `/ask <persona> <question>`
Ask a question to a specific AI persona.

**Parameters:**
- `persona`: Name of the persona to query (autocomplete available)
- `question`: Your question or prompt

**Example:**
```
/ask TechExpert How do I optimize my Python code for better performance?
```

**Features:**
- Autocomplete suggestions for available personas
- Smart persona recommendations if wrong persona selected
- Channel restriction enforcement
- Rate limit checking
- Cooldown management
- Response includes remaining usage quota

**Response Format:**
- Persona name and avatar
- AI-generated answer
- Original question excerpt
- Usage statistics (remaining daily/weekly uses)
- Response token limit indicator

---

### `/personas`
Display all available AI personas in the server.

**Features:**
- Shows top 10 most-used personas
- Displays description, limits, and restrictions
- Usage statistics for each persona
- Channel and role restrictions overview
- Sorted by popularity

**Information Displayed:**
- Persona description
- Response token limit
- Cooldown period
- Total usage count
- Default rate limits
- Active restrictions

---

### `/personainfo <persona>`
Get detailed information about a specific persona.

**Parameters:**
- `persona`: Name of the persona (autocomplete available)

**Information Provided:**
- Full description
- Configuration details (response limit, cooldown, rate limits)
- Usage statistics and creation date
- Active restrictions (required role, channels, role limits)
- System prompt preview (first 200 characters)
- Usage instructions

---

### `/adminpanel`
Open the comprehensive administration panel (Admins and Manager Role only).

**Access Requirements:**
- Server Administrator permission, OR
- Assigned Manager Role

---

## Administration Panel

### Main Dashboard

The main dashboard provides an at-a-glance overview of your bot configuration:

**API Configuration Section:**
- API status indicator (active/not configured)
- Encryption status
- Current AI model

**Access Control Section:**
- Manager role status
- Permission overview

**Personas Overview:**
- Total persona count
- Total usage across all personas
- Average usage per persona

**Global Settings:**
- Default cooldown period
- Default token limit
- Smart suggestions status

**Quick Stats:**
- Most used persona
- Total configured channels
- Total role configurations

**Navigation Buttons:**
- 🎭 Personas
- ⚙️ Settings
- 📊 Statistics
- 🚀 Quick Setup (appears if setup incomplete)
- 🔄 Refresh

---

### 🎭 Personas Tab

Comprehensive persona management interface with pagination.

#### Features:
- **Paginated List**: Shows 5 personas per page
- **Quick Action Buttons**: Numbered buttons for each persona
- **Create New Persona**: ➕ button to add personas
- **Navigation**: First, Previous, Next, Last page controls

#### Persona Quick Actions:
When clicking a numbered persona button:

**🔧 Edit Core**: Modify fundamental settings
- Persona name
- Description
- System prompt
- Response length limit
- Required role ID

**⚙️ Settings**: Adjust operational parameters
- Cooldown period
- Default daily limit
- Default weekly limit

**📢 Channels**: Manage channel restrictions
- Multi-select channel picker
- Clear restrictions option
- Visual list of allowed channels

**🎫 Required Role**: Set mandatory role requirement
- Single role enforcement
- All users must have this role to use persona
- Different from role-specific rate limits

**🎫 Role Limits**: Configure role-based rate limiting
- Add role-specific daily/weekly limits
- Edit existing role limits
- Delete role configurations
- Paginated role list view

**🗑️ Delete**: Remove persona permanently
- Confirmation dialog
- Irreversible action
- Removes all associated data

---

### ⚙️ Settings Tab

Global bot configuration management.

#### Available Settings:

**🔑 Set API Key**
- Enter or update Gemini API key
- Automatic validation
- Encrypted storage
- Guild-specific encryption

**👑 Set Manager Role**
- Assign a role for panel access
- Manager role members can use `/adminpanel`
- Does not override Administrator permissions

**🤖 Set Model**
- Choose Gemini AI model variant
- Options include:
  - gemini-2.5-flash-lite (default, fast)
  - gemini-2.0-flash-exp (experimental)
  - Other Gemini models

**🌐 Global Settings**
- **Default Cooldown**: Base cooldown for new personas (seconds)
- **Default Response Limit**: Base token limit for new personas
- **Enable Smart Suggestions**: Toggle persona recommendation system

---

### 📊 Statistics Tab

Detailed analytics and usage insights.

#### Displayed Information:

**🏆 Top 5 Most Used Personas**
- Visual bar chart representation
- Usage count and percentage
- Ranked by total uses

**📈 Overall Statistics**
- Total requests across all personas
- Number of active personas
- Average requests per persona

**🎯 Configuration Summary**
- Count of restricted personas
- Total channel restrictions
- Total role configurations

**📊 Usage Range**
- Most active persona
- Least active persona
- Usage comparison

#### Available Actions:

**🔄 Reset Stats**
- Clear all usage counters
- Confirmation required
- Irreversible action

**📥 Export Stats**
- Download detailed statistics as text file
- Includes all personas with full metrics
- Timestamped export

**🔄 Refresh**
- Update statistics in real-time

---

## Rate Limiting System

### How Rate Limits Work

ZAI implements a sophisticated three-tier rate limiting system:

#### 1. Default Rate Limits
Applied to all users by default:
- Daily limit (default: 50 uses)
- Weekly limit (default: 300 uses)
- Configurable per persona

#### 2. Role-Based Rate Limits
Override default limits for specific roles:
- Set higher/lower limits per role
- Useful for premium members, moderators, or restricted users
- Multiple roles can have different limits
- Highest limit applies if user has multiple configured roles

#### 3. Required Role Enforcement
Completely restrict persona access:
- Users MUST have the specified role
- No usage allowed without the role
- Separate from rate limiting
- Useful for exclusive content or privileged assistants

### Rate Limit Resets
- **Daily limits**: Reset every 24 hours from first use
- **Weekly limits**: Reset every 168 hours (7 days) from first use
- Automatic tracking per user, per persona, per guild

### Rate Limit Messages
When rate limits are reached, users receive:
- Current usage counts (daily/weekly)
- Maximum allowed uses
- Time until reset (hours remaining)
- Clear error message

---

## Cooldown System

### Purpose
Prevents spam and ensures fair resource distribution.

### Configuration
- Set per persona (default: 5 seconds)
- Configurable from 1 to 99999 seconds
- Independent of rate limits

### Behavior
- Timer starts after successful request
- Applies per user, per persona
- Does not consume rate limit quota if triggered
- Clear countdown message displayed

---

## Channel Restrictions

### Purpose
Limit persona usage to specific channels.

### Configuration
1. Open persona quick actions
2. Click **📢 Channels**
3. Select up to 25 channels
4. Submit to apply restrictions

### Behavior
- If channels are configured: persona only works in those channels
- If no channels configured: persona works in all channels
- Clear error message when used in wrong channel
- Shows list of allowed channels

---

## Persona Redirect System

### Intelligent Question Routing

ZAI personas can recognize when a question doesn't match their expertise and redirect users to more appropriate personas.

### How It Works

1. **Question Analysis**: The AI analyzes if the question fits its expertise
2. **Redirect Decision**: If inappropriate, suggests a better-suited persona
3. **Redirect Loop Prevention**: Maximum 2 redirects per question
4. **Fallback Message**: After 2 redirects, informs user no suitable persona exists

### Redirect Format

When a persona redirects:
```
I appreciate your question, but as [PersonaName], I'm not the best fit for this. 
I'd recommend asking [BetterPersona] instead - they specialize in [reason]. 
You can ask them using: /ask [BetterPersona] your question here
```

### Loop Prevention

If multiple personas redirect the same question:
- Bot detects circular redirects
- Displays all attempted personas
- Provides suggestions:
  - Rephrase the question
  - Check available personas with `/personas`
  - Contact moderator for new persona creation

### Invalid Persona Detection

If a persona suggests a non-existent persona:
- Warning message displayed
- Explains the suggested persona doesn't exist
- Suggests contacting administrators
- Shows how to view available personas

---

## Smart Persona Suggestions

### Automatic Recommendation System

When users select the wrong persona, ZAI suggests alternatives.

### How It Works

**Keyword Analysis**: Matches question keywords to persona descriptions
- Tech keywords: code, programming, software, etc.
- Lore keywords: story, history, character, etc.
- Debate keywords: argue, opinion, versus, etc.
- Comedy keywords: joke, funny, humor, etc.
- Support keywords: help, problem, fix, etc.
- Creative keywords: write, create, design, etc.
- Math keywords: calculate, equation, solve, etc.
- Science keywords: experiment, research, physics, etc.

**Scoring System**:
- Category matching in persona name/description: +10 per keyword
- Keywords in system prompt: +5 per keyword
- Common words between question and description: +2 per word

**Threshold**: Suggestions only shown if score > 5

### Disabling Suggestions
1. Open `/adminpanel`
2. Go to **Settings** tab
3. Click **🌐 Global Settings**
4. Set "Enable Smart Suggestions" to "no"

---

## Response Token Limits

### Purpose
Control response length and API costs.

### Configuration
- Set per persona (default: 500 tokens)
- Range: 1 to 9999 tokens
- Approximately 4 characters per token

### Token Guidelines:
- **100 tokens**: Very short response (~75 words)
- **500 tokens**: Medium response (~375 words)
- **1000 tokens**: Long response (~750 words)
- **2000 tokens**: Very long response (~1500 words)

### Behavior
- AI generates up to the specified limit
- Responses may be shorter if answer is complete
- Longer limits allow more detailed responses
- Higher tokens = more API usage/cost

---

## System Prompt Best Practices

### What is a System Prompt?

The system prompt defines the AI's personality, expertise, behavior, and response style. It's the most important configuration for each persona.

### Effective System Prompts Should:

1. **Define Role Clearly**
   - "You are a senior Python developer with 10 years of experience"
   - "You are a friendly cooking instructor specializing in Italian cuisine"

2. **Specify Expertise Areas**
   - "Your expertise includes web development, APIs, and database design"
   - "You specialize in medieval European history, particularly 12th-15th centuries"

3. **Set Tone and Style**
   - "Use friendly, encouraging language suitable for beginners"
   - "Provide technical, precise answers with code examples"
   - "Write in a casual, humorous tone with pop culture references"

4. **Establish Boundaries**
   - "If asked about topics outside programming, politely redirect to appropriate personas"
   - "Do not provide medical advice; recommend consulting professionals"

5. **Include Response Guidelines**
   - "Always provide code examples when relevant"
   - "Structure answers with clear headings and bullet points"
   - "Keep responses concise and under 3 paragraphs"

### Example System Prompts

**Technical Expert:**
```
You are TechMaster, a senior software engineer with expertise in Python, JavaScript, 
databases, and system architecture. Provide clear, practical solutions with code 
examples. Explain complex concepts simply. If asked about non-technical topics, 
recommend the appropriate persona. Always consider best practices and security.
```

**Creative Writer:**
```
You are StoryWeaver, a creative writing mentor specializing in fiction, worldbuilding, 
and character development. Provide constructive feedback, inspire creativity, and 
offer practical writing techniques. Use vivid language and examples. If asked about 
technical or non-creative topics, redirect to appropriate personas.
```

**Support Helper:**
```
You are HelpBot, a patient technical support specialist. Guide users through 
troubleshooting step-by-step. Ask clarifying questions when needed. Use simple 
language and avoid jargon. Provide clear, actionable solutions. If the issue 
requires human intervention, recommend contacting server moderators.
```

---

## Data Storage & Privacy

### Encrypted Data
- API keys encrypted using AES-256
- Guild-specific encryption keys
- Keys derived from server ID (cannot be used across servers)

### Stored Data
- Server configuration (API key, manager role, model, global settings)
- Persona definitions (prompts, descriptions, limits, restrictions)
- Usage statistics (per-persona counters)
- No message content stored
- No user conversation history stored

### Data Location
All data stored locally in:
```
data/airolebasedhelper/[guild_id]/config.json
```

### Data Persistence
- Configuration persists across bot restarts
- Usage statistics continue accumulating
- Cooldowns and rate limits reset on restart
- Session data cleared after 1 hour of inactivity

---

## Troubleshooting

### "API key not configured"
**Solution**: 
1. Use `/adminpanel`
2. Go to Settings tab
3. Click "🔑 Set API Key"
4. Enter valid Gemini API key

### "You don't have permission to use this panel"
**Solution**: 
- Must be Server Administrator, OR
- Must have the configured Manager Role
- Contact server owner if needed

### "Persona not found"
**Solution**: 
- Check spelling (case-sensitive)
- Use autocomplete when typing `/ask`
- Use `/personas` to see available options
- Contact admin if persona should exist

### "Rate limit reached"
**Solution**: 
- Wait for daily/weekly reset (time shown in error)
- Contact admin to increase your role's limits
- Check if you have appropriate role for higher limits

### "Channel restriction"
**Solution**: 
- Use persona in one of the allowed channels (list shown in error)
- Contact admin to add your channel
- Check if channel list is correct

### "Missing required role"
**Solution**:
- Obtain the required role from moderators
- Contact admin if role requirement is incorrect
- Check `/personainfo` to see which role is needed

### "Cooldown active"
**Solution**: 
- Wait the specified seconds (shown in error)
- Normal behavior to prevent spam
- Contact admin if cooldown seems too long

### API Validation Failed
**Solution**: 
- Verify API key is correct
- Check API key has not expired
- Ensure API key has Gemini API access enabled
- Try generating a new key from Google AI Studio

### Responses are cut off
**Solution**: 
- Increase response token limit for that persona
- Edit persona via `/adminpanel` → Personas → Edit Core
- Adjust to higher value (e.g., 1000 or 2000 tokens)

### Persona redirects incorrectly
**Behavior**: Persona suggests another persona that doesn't fit either
**Solution**: 
- System detects redirect loops after 2 attempts
- Improve system prompts to be more specific about boundaries
- Consider creating new persona for that topic
- Report persistent issues to bot developer

### Statistics not updating
**Solution**: 
- Click Refresh button in Statistics tab
- Statistics update in real-time per request
- Check if persona is actually being used

---

## Best Practices for Server Admins

### Security
- Keep API key private (only admins should have access)
- Review Manager Role members regularly
- Use channel restrictions for sensitive personas
- Set appropriate rate limits to prevent abuse

### Persona Design
- Create 3-5 specialized personas rather than one general-purpose
- Write detailed system prompts (200-500 words recommended)
- Test personas thoroughly before announcing
- Update descriptions to match actual behavior

### Rate Limiting Strategy
- Set default limits conservatively (50/day, 300/week)
- Create higher limits for trusted roles (moderators, VIP)
- Lower limits for new members or trial periods
- Monitor usage statistics to adjust limits

### Channel Organization
- Restrict technical personas to tech channels
- General-purpose personas can be unrestricted
- Entertainment personas in casual channels
- Help/support personas in support channels

### User Education
- Announce new personas with examples
- Pin `/personas` command results
- Create channel with persona guides
- Provide example questions for each persona

### Maintenance
- Review statistics monthly
- Remove unused personas
- Update prompts based on user feedback
- Export statistics for records
- Check for redirect loops or confusion

---

## Advanced Configuration Examples

### Premium Tier System

**Setup**:
1. Create role "Premium Member"
2. Configure standard personas with default limits
3. Add role limit overrides:
   - Premium Members: 200/day, 1000/week
   - Regular Members: 50/day, 300/week

### Support Ticket System

**Setup**:
1. Create "SupportBot" persona
2. Restrict to #support channel only
3. Set high response limit (1500 tokens)
4. System prompt includes escalation procedures
5. No rate limits for staff roles

### Educational Server

**Setup**:
1. Create specialized subject personas (Math, Science, History)
2. Restrict each to subject-specific channels
3. Required roles: "Verified Student"
4. Moderate rate limits for study support
5. Export statistics for engagement tracking

### Gaming Community

**Setup**:
1. "LoreKeeper" - Game world information
2. "StrategyMaster" - Build and tactic advice
3. "EventBot" - Event information and schedules
4. "NewbieHelper" - Beginner-friendly explanations
5. Channel restrictions per game/topic

---

## FAQ

**Q: How many personas can I create?**
A: Unlimited. However, 5-10 well-designed personas are more effective than 50 unfocused ones.

**Q: Can personas access previous messages?**
A: No. Each request is independent with no conversation history. Design prompts accordingly.

**Q: Can I export persona configurations?**
A: Currently only statistics export is available. Configuration backup requires manual JSON file copying.

**Q: What happens if I change the API key?**
A: New key takes effect immediately. Previous responses remain but new requests use new key/billing.

**Q: Can users see system prompts?**
A: Only first 200 characters via `/personainfo`. Full prompt is admin-only.

**Q: Do cooldowns stack across personas?**
A: No. Each persona has independent cooldown timers per user.

**Q: Can I set different models per persona?**
A: No. Model selection is global across all personas.

**Q: What happens when I delete a persona?**
A: Immediate permanent deletion including all statistics. User rate limit tracking is also cleared.

**Q: Can personas learn from interactions?**
A: No. Each request is stateless. Personas respond based only on their system prompt and the current question.

**Q: How are rate limits enforced across roles?**
A: If a user has multiple roles with configured limits, the highest limit applies.

**Q: Can I temporarily disable a persona?**
A: No direct disable function. Workarounds: Set required role to admin-only, or restrict to unused channel.

**Q: Does the bot support multiple languages?**
A: The interface is English, but personas can be prompted to respond in any language Gemini supports.

---

## Support & Credits

### License
Custom License Agreement - All Rights Reserved
Copyright © 2025 TheHolyOneZ (TheZ)

**Restrictions**:
- No modification allowed
- No redistribution
- No code reuse
- Educational reading permitted
- Report bugs to developer

### Powered By
- **Google Gemini AI**: Underlying language model
- **Discord.py**: Discord bot framework
- **Python Cryptography**: Encryption services

### Attribution Requirements
When using this bot, the following credits must remain intact:
- TheHolyOneZ / TheZ (Developer)
- Zygnalbot (Platform)
- ZAIRoleBasedHelper (Software name)
- Powered by Gemini (AI attribution)

### Getting Help
- Report bugs directly to TheHolyOneZ (TheZ)
- Visit: zygnalbot.com/extension/
- Official Zygnalbot Marketplace

### Do Not
- Attempt to fix bugs yourself (report only)
- Remove or alter attribution
- Share bot files with others
- Modify the code
- Claim as your own work

---

## Version Information



**Features in This Version**:
- Multi-persona AI system with Gemini integration
- Encrypted API key storage
- Advanced admin panel with tabs and pagination
- Role-based rate limiting
- Channel restrictions
- Required role enforcement
- Smart persona suggestions
- Redirect loop prevention
- Usage statistics and export
- Cooldown management
- Real-time quota tracking
- Autocomplete support
- Modal-based configuration
- Comprehensive error handling

---

*This bot is designed to enhance community engagement through intelligent, customizable AI interactions while maintaining security, fairness, and administrative control.*
