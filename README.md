## Intro To AI Agents with Snowflake Cortex Tutorial

This is a Snowflake Cortex Agent presentation project containing a Jupyter notebook demonstrating Snowflake Cortex AI capabilities. The project consists of a single tutorial notebook that shows how to interact with Snowflake's Cortex Agent API for sales intelligence analytics.

## Architecture

### Core Components

- **grc_cortex_tutorial.ipynb**: Main tutorial notebook demonstrating Cortex Agent usage
- The notebook uses Snowflake's `_snowflake` module and Snowpark for database connectivity
- Integrates with two main Cortex tools:
  - Cortex Analyst (text-to-SQL generation)  
  - Cortex Search (semantic search capabilities)

### Key Configuration

The notebook is configured to work with:
- **Model**: Claude-4-Sonnet via Cortex Agent API
- **Semantic Models**: `@sales_intelligence.data.models/sales_metrics_model_grc.yaml`
- **Search Service**: `sales_intelligence.data.sales_conversation_search`
- **API Endpoint**: `/api/v2/cortex/agent:run`

## Development Environment

This is a Snowflake-based project that requires:
- Active Snowpark session (obtained via `get_active_session()`)
- Access to the `_snowflake` internal module
- Permissions to access the configured semantic models and search services

## Running the Notebook

The notebook demonstrates two main patterns:
1. Weekly sales metrics summaries with multiple tools
2. Revenue analysis for closed deals by time period

Each cell follows the pattern:
1. Define a natural language prompt
2. Configure payload with tools and resources
3. Call the Cortex Agent API
4. Parse response events for assistant text and generated SQL
5. Execute SQL and display results

## Working with This Code

When modifying the notebook:
- The API timeout is set to 50 seconds for complex queries
- Tool resources must match existing Snowflake objects
- Generated SQL is cleaned of semicolons before execution
- Assistant text includes reference markers that are cleaned with regex replacement
