#  AI-Powered SQL Agent for n8n
by R.H. Amezqueta

N8n workflow that transforms natural language questions into SQL queries and provides intelligent, conversational responses based on your database data.

## What This Workflow Does

This workflow creates an intelligent database assistant that can understand plain English questions and automatically:

1. **Convert natural language to SQL**: Takes questions like "How many customers do we have?" and converts them into proper SQL queries
2. **Execute database queries safely**: Runs read-only SELECT statements on your PostgreSQL database
3. **Provide conversational responses**: Returns human-friendly answers based on the actual data results


### Example Flow:

**Input**: "What are the top 5 best-selling products?"

**Process**: 
- AI converts question to: `SELECT product_name, sales_count FROM products ORDER BY sales_count DESC LIMIT 5`
- Executes query on database
- Formats results into readable context

**Output**: "Based on your sales data, the top 5 best-selling products are: Product A (1,250 sales), Product B (1,100 sales), Product C (950 sales), Product D (800 sales), and Product E (750 sales)."

##  Key Components

- **Webhook Trigger**: Receives questions via HTTP API
- **Google Gemini AI**: Converts natural language to SQL queries
- **PostgreSQL Integration**: Executes safe database queries
- **Ollama AI**: Generates conversational responses
- **Safety Features**: Only allows SELECT statements, prevents data modification

##  Use Cases

- **Customer Support**: "How many orders did customer X place last month?"
- **Business Analytics**: "What's our average order value this quarter?"
- **Inventory Management**: "Which products are running low on stock?"
- **Reporting**: "Show me sales trends for the past 6 months"
- **Data Exploration**: "What are our most popular product categories?"

##  Safety Features

- **Read-Only Access**: Only generates SELECT statements, never INSERT, UPDATE, or DELETE
- **AI-Powered Security**: Uses intelligent query generation to prevent SQL injection
- **Controlled Access**: Works within defined database schema and permissions
- **Data Privacy**: The cloud LLM (Google Gemini) only sees your questions and generates SQL queries - it never sees your actual database data or results

##  Limitations

- **No Memory**: Each query is processed independently - the workflow doesn't remember previous conversations or context (though any memory tool can be easily added)
- **Query-Only**: Only handles questions that can be answered with database queries - general chat or non-data questions are not supported (but can be adapted to user-specific handling requirements)

##  Integration

The workflow exposes a simple webhook API that accepts natural language questions and returns intelligent responses, making it easy to integrate into:

- Chat applications
- Customer support systems
- Business intelligence dashboards
- Mobile apps
- Web interfaces

Perfect for anyone who wants to make their database accessible through natural language without compromising security or requiring SQL knowledge from end users.

<br>by R.H. Amezqueta
