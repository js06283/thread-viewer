# Thread Viewer

A standalone web application for viewing OpenAI Assistant conversations and code interpreter outputs.

## Features

- View all assistant conversations in a clean, organized interface
- Display code inputs and outputs with syntax highlighting
- Show function calls and responses
- Display file search results
- Toggle code blocks for better readability
- Auto-refresh every 30 seconds
- Responsive design for mobile and desktop

## Deployment

This is a static HTML application that can be deployed to Vercel.

### Prerequisites

- Vercel CLI installed (`npm i -g vercel`)
- Access to the OpenAI proxy backend API

### Deployment Steps

1. Make sure you're in the thread-viewer directory
2. Update the `API_BASE_URL` in `index.html` to point to your OpenAI proxy backend
3. Deploy to Vercel:

```bash
vercel
```

4. Follow the prompts to create a new project
5. Your thread viewer will be available at the provided Vercel URL

### Configuration

The thread viewer connects to the OpenAI proxy backend API at `/api/threads`. Make sure:

1. The backend is deployed and accessible
2. CORS is properly configured on the backend
3. The `API_BASE_URL` in `index.html` points to the correct backend URL

## Usage

1. Open the deployed thread viewer URL
2. Click "Refresh Threads" to load the latest conversations
3. Click on any thread to expand and view messages
4. Use the toggle buttons to show/hide code blocks
5. The page auto-refreshes every 30 seconds

## API Endpoint

The thread viewer expects the backend to provide data at `/api/threads` with the following structure:

```json
{
	"threads": [
		{
			"threadId": "thread_abc123",
			"messages": [
				{
					"role": "user|assistant",
					"content": "message content",
					"timestamp": "2024-01-01T00:00:00.000Z",
					"contentType": "text|code_input|code_output|function_call|etc"
				}
			]
		}
	]
}
```
