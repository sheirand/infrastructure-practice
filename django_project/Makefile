PROJECT_NAME=django_project

postgres: ## Runs or starts postgres database
	@if [ $(shell docker ps -qa -f name=$(PROJECT_NAME)-db) ]; then \
          docker start $(PROJECT_NAME)-db; \
     else \
		  docker run -d -p 5432:5432 \
				  -e POSTGRES_PASSWORD=$(PROJECT_NAME) \
				  -e POSTGRES_USER=$(PROJECT_NAME) \
				  -e POSTGRES_DB=$(PROJECT_NAME) \
				  --name $(PROJECT_NAME)-db \
				  --restart always \
				  postgres:13; \
      fi