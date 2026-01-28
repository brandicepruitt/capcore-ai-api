# CapCore Systems - Elite AI API v3.0.0

## What's Included

**13 Elite AI Specialists across 3 Pillars + General Assistant:**

### Pillar 1: SmartHire Toolkit (6 GPTs)
| GPT | Endpoint | Purpose |
|-----|----------|---------|
| Resume Specialist | `/api/assistants/resume` | Elite ATS optimization and resume architecture |
| Cover Letter Specialist | `/api/assistants/coverLetter` | Compelling career narratives |
| Interview Coach | `/api/assistants/interview` | Interview mastery and STAR method |
| LinkedIn Optimizer | `/api/assistants/linkedin` | Profile optimization for recruiters |
| Salary Negotiation Strategist | `/api/assistants/salary` | Compensation intelligence |
| Job Search Strategist | `/api/assistants/jobSearch` | Hidden job market access |

### Pillar 2: AI Career Accelerator (2 GPTs) - NEW
| GPT | Endpoint | Purpose |
|-----|----------|---------|
| **Networking Pro** | `/api/assistants/networking` | Professional outreach and relationship building |

### Pillar 3: AI Business Builder (4 GPTs) - ENHANCED
| GPT | Endpoint | Purpose |
|-----|----------|---------|
| LinkedInPro AI | `/api/assistants/linkedinpro` | Content strategy and thought leadership |
| PeopleLeader AI | `/api/assistants/peopleleader` | HR strategy and people management |
| DocMaster AI | `/api/assistants/docmaster` | Proposals, contracts, SOWs |
| **Business Strategy AI** | `/api/assistants/businessStrategy` | Business model and growth strategy |

### General
| GPT | Endpoint | Purpose |
|-----|----------|---------|
| CapCore Concierge | `/api/assistants/smart` | Product guidance and routing |

## Deployment Instructions

### Step 1: Upload to GitHub

1. Go to your repository: `github.com/brandicepruitt/capcore-ai-api`
2. Delete all existing files (or create fresh)
3. Upload these 3 files:
   - `server.js`
   - `package.json`
   - `Dockerfile`
4. Commit with message: "Upgrade to Elite v3.0.0 - 13 AI Specialists"

### Step 2: Railway Auto-Deploy

Railway will automatically detect the changes and redeploy.

If it doesn't auto-deploy:
1. Go to Railway dashboard
2. Click on your `capcore-ai-api` service
3. Click "Deploy" on the pending deployment

### Step 3: Verify

Test these endpoints:

**Health Check:**
```
https://capcore-ai-api-production.up.railway.app/health
```
Should return: `{"status":"healthy","version":"3.0.0","edition":"Elite","specialists":13}`

**Specialists List:**
```
https://capcore-ai-api-production.up.railway.app/api/assistants/specialists
```
Should show all 13 specialists organized by category.

## API Usage

### Chat with Specific Specialist
```bash
POST /api/assistants/{specialistId}

{
  "message": "Your message here",
  "conversationHistory": []
}
```

### Smart Chat (Auto-Routes)
```bash
POST /api/chat

{
  "message": "Your message here",
  "specialist": "auto"
}
```

## Environment Variables (Already Set in Railway)

- `ANTHROPIC_API_KEY` - Your Claude API key
- `ALLOWED_ORIGINS` - capcoresystems.com
- `NODE_ENV` - production

## Version History

- **v1.0.0** - Basic chat widget
- **v2.0.0** - 10 Specialized GPTs
- **v3.0.0** - Elite Edition: 13 GPTs with enhanced prompts, new Networking Pro and Business Strategy GPTs
