# CapCore AI API Server v2.0.0

Complete AI API server for CapCore Systems with 10 specialized GPT assistants.

## Specialists Included

### SmartHire Toolkit (6 specialists)
| Specialist | Endpoint | Description |
|------------|----------|-------------|
| Resume Specialist | `/api/assistants/resume` | ATS optimization, resume writing |
| Cover Letter Specialist | `/api/assistants/cover-letter` | Compelling cover letters |
| Interview Coach | `/api/assistants/interview` | Mock interviews, STAR method |
| LinkedIn Optimizer | `/api/assistants/linkedin` | Profile optimization |
| Salary Negotiation | `/api/assistants/salary` | Compensation strategy |
| Job Search Strategy | `/api/assistants/job-search` | Job search planning |

### AI Business Assistants (3 specialists)
| Specialist | Endpoint | Description |
|------------|----------|-------------|
| LinkedInPro AI | `/api/assistants/linkedinpro` | Content strategy & ghostwriting |
| PeopleLeader AI | `/api/assistants/peopleleader` | HR & management support |
| DocMaster AI | `/api/assistants/docmaster` | Proposals, contracts, documents |

### General
| Specialist | Endpoint | Description |
|------------|----------|-------------|
| Smart Assistant | `/api/assistants/smart` | General guide & routing |

## API Endpoints

### Health Check
```
GET /health
```

### List Specialists
```
GET /api/assistants/specialists
```

### Main Chat (with auto-routing)
```
POST /api/assistants/chat
Body: {
  "message": "Help me with my resume",
  "specialist": "auto",  // or specific specialist ID
  "conversationHistory": []
}
```

### Direct Specialist Access
```
POST /api/assistants/{specialist}
Body: {
  "message": "Your message here",
  "conversationHistory": []
}
```

## Deployment to Railway

### Step 1: Update GitHub Repository

1. Go to your GitHub repository: `github.com/[your-username]/capcore-ai-api`
2. Delete all existing files (or replace them)
3. Upload these files:
   - `server.js`
   - `package.json`
   - `Dockerfile`
   - `.env.example`
4. Commit the changes

### Step 2: Railway Auto-Deploys

Railway will automatically detect the changes and redeploy. Wait 2-3 minutes.

### Step 3: Verify Deployment

1. Go to: `https://capcore-ai-api-production.up.railway.app/health`
   - Should return: `{"status":"healthy","timestamp":"...","version":"2.0.0"}`

2. Go to: `https://capcore-ai-api-production.up.railway.app/api/assistants/specialists`
   - Should return list of all 10 specialists

### Step 4: Test a Specialist

```bash
curl -X POST https://capcore-ai-api-production.up.railway.app/api/assistants/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Help me optimize my resume for ATS", "specialist": "auto"}'
```

## Environment Variables (Already Set in Railway)

- `ANTHROPIC_API_KEY` - Your Claude API key
- `NODE_ENV` - Set to `production`
- `ALLOWED_ORIGINS` - Your website domains

## Local Development

```bash
# Install dependencies
npm install

# Create .env file
cp .env.example .env
# Edit .env with your API key

# Run in development
npm run dev

# Run in production
npm start
```

## Version History

- v2.0.0 - Complete rewrite with 10 specialized GPTs
- v1.0.0 - Basic chat functionality

## Support

For issues, contact CapCore Systems support.
