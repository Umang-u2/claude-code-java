# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands
- Build: `mvn package`
- Run: `./your_program.sh`
- Test/Submit: `codecrafters submit`
- Run single test: Not applicable (no local test suite), but standard Maven command is `mvn test -Dtest=ClassName`

## Architecture
The project is a minimal Java application acting as a CLI bridge to the OpenRouter API.
- **Structure**: Standard Maven layout with a single entry point in `src/main/java/Main.java`.
- **Flow**: CLI Arguments $\rightarrow$ `Main.main()` $\rightarrow$ `OpenAIClient` (via `openai-java` SDK) $\rightarrow$ `OpenRouter API` $\rightarrow$ Standard Output.
- **Configuration**: Uses `OPENROUTER_API_KEY` and `OPENROUTER_BASE_URL` environment variables.
- **Target Model**: Configured to use `anthropic/claude-haiku-4.5`.
