```markdown
# Kaiburr Task Management API

A Spring Boot REST API for task management with MongoDB integration.

## 🚀 Quick Start

### Prerequisites
- Java 17
- Maven 3.6+
- MongoDB 4.4+

### Installation & Setup

1. **Clone and navigate to project**
```bash
cd kaiburr-task1
```

2. **Verify Java installation**
```bash
java -version
```

3. **Start MongoDB**
```bash
brew services start mongodb-community
```

4. **Run the application**
```bash
mvn clean spring-boot:run
```

Application starts at: `http://localhost:8080`

## 📚 API Usage

### Base URL
```
http://localhost:8080/api/tasks
```

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/tasks` | Get all tasks |
| GET | `/api/tasks/{id}` | Get task by ID |
| GET | `/api/tasks/name/{name}` | Search tasks by name |
| GET | `/api/tasks/assignee/{assignee}` | Search tasks by assignee |
| POST | `/api/tasks` | Create new task |
| PUT | `/api/tasks/{id}` | Update task |
| DELETE | `/api/tasks/{id}` | Delete task |

### Examples

**Create a task:**
```bash
curl -X POST http://localhost:8080/api/tasks \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Develop API",
    "assignee": "John Doe",
    "project": "Kaiburr Project",
    "startTime": "2025-10-20"
  }'
```

**Get all tasks:**
```bash
curl http://localhost:8080/api/tasks
```

**Search tasks by name:**
```bash
curl http://localhost:8080/api/tasks/name/Develop
```

**Update a task:**
```bash
curl -X PUT http://localhost:8080/api/tasks/123 \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Updated Task",
    "assignee": "Jane Smith",
    "project": "New Project",
    "startTime": "2025-10-21"
  }'
```

**Delete a task:**
```bash
curl -X DELETE http://localhost:8080/api/tasks/123
```

## 🛠️ Development

### Project Structure
```
src/main/java/com/example/kaiburrtask1/
├── controller/TaskController.java
├── service/TaskService.java
├── repository/TaskRepository.java
├── model/Task.java
└── util/CommandValidator.java
```

### Build Commands
```bash
# Compile
mvn clean compile

# Package
mvn clean package

# Run tests
mvn test

# Run application
mvn spring-boot:run
```

## ⚙️ Configuration

### Default Settings
- **Port**: 8080
- **MongoDB**: localhost:27017
- **Database**: Auto-configured

### Custom Configuration
Edit `src/main/resources/application.properties`:
```properties
server.port=9090
spring.data.mongodb.uri=mongodb://localhost:27017/taskdb
```

## 🐛 Troubleshooting

### Common Issues

**Application won't start:**
- Check if MongoDB is running: `brew services list | grep mongodb`
- Verify Java version: `java -version`

**404 errors on endpoints:**
- Ensure application is running
- Check endpoint URLs start with `/api/tasks`

**Port already in use:**
```bash
# Kill process on port 8080
lsof -ti:8080 | xargs kill -9
```

**Java version issues:**
```bash
# Set Java 17 home
export JAVA_HOME=$(/usr/libexec/java_home -v 17)
```

## 📦 Deployment

### Run JAR directly:
```bash
java -jar target/kaiburr-task1-0.0.1-SNAPSHOT.jar
```

### Docker Deployment:
```dockerfile
FROM openjdk:17-jdk-slim
COPY target/kaiburr-task1-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app.jar"]
```

## 📝 API Response Format

**Success Response:**
```json
{
  "id": "650a1b2c3d4e5f6a7b8c9d0e",
  "name": "Task Name",
  "assignee": "Assignee Name",
  "project": "Project Name",
  "startTime": "2025-10-20"
}
```

**Error Response:**
```json
{
  "timestamp": "2025-10-20T13:05:44.567+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/api/invalid-endpoint"
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

**Note**: Make sure MongoDB is running before starting the application. The API uses MongoDB to store all task data.
``````markdown
# Kaiburr Task Management API

A Spring Boot REST API for task management with MongoDB integration.

## 🚀 Quick Start

### Prerequisites
- Java 17
- Maven 3.6+
- MongoDB 4.4+

### Installation & Setup

1. **Clone and navigate to project**
```bash
cd kaiburr-task1
```

2. **Verify Java installation**
```bash
java -version
```

3. **Start MongoDB**
```bash
brew services start mongodb-community
```

4. **Run the application**
```bash
mvn clean spring-boot:run
```

Application starts at: `http://localhost:8080`

## 📚 API Usage

### Base URL
```
http://localhost:8080/api/tasks
```

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/tasks` | Get all tasks |
| GET | `/api/tasks/{id}` | Get task by ID |
| GET | `/api/tasks/name/{name}` | Search tasks by name |
| GET | `/api/tasks/assignee/{assignee}` | Search tasks by assignee |
| POST | `/api/tasks` | Create new task |
| PUT | `/api/tasks/{id}` | Update task |
| DELETE | `/api/tasks/{id}` | Delete task |

### Examples

**Create a task:**
```bash
curl -X POST http://localhost:8080/api/tasks \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Develop API",
    "assignee": "John Doe",
    "project": "Kaiburr Project",
    "startTime": "2025-10-20"
  }'
```

**Get all tasks:**
```bash
curl http://localhost:8080/api/tasks
```

**Search tasks by name:**
```bash
curl http://localhost:8080/api/tasks/name/Develop
```

**Update a task:**
```bash
curl -X PUT http://localhost:8080/api/tasks/123 \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Updated Task",
    "assignee": "Jane Smith",
    "project": "New Project",
    "startTime": "2025-10-21"
  }'
```

**Delete a task:**
```bash
curl -X DELETE http://localhost:8080/api/tasks/123
```

## 🛠️ Development

### Project Structure
```
src/main/java/com/example/kaiburrtask1/
├── controller/TaskController.java
├── service/TaskService.java
├── repository/TaskRepository.java
├── model/Task.java
└── util/CommandValidator.java
```

### Build Commands
```bash
# Compile
mvn clean compile

# Package
mvn clean package

# Run tests
mvn test

# Run application
mvn spring-boot:run
```

## ⚙️ Configuration

### Default Settings
- **Port**: 8080
- **MongoDB**: localhost:27017
- **Database**: Auto-configured

### Custom Configuration
Edit `src/main/resources/application.properties`:
```properties
server.port=9090
spring.data.mongodb.uri=mongodb://localhost:27017/taskdb
```

## 🐛 Troubleshooting

### Common Issues

**Application won't start:**
- Check if MongoDB is running: `brew services list | grep mongodb`
- Verify Java version: `java -version`

**404 errors on endpoints:**
- Ensure application is running
- Check endpoint URLs start with `/api/tasks`

**Port already in use:**
```bash
# Kill process on port 8080
lsof -ti:8080 | xargs kill -9
```

**Java version issues:**
```bash
# Set Java 17 home
export JAVA_HOME=$(/usr/libexec/java_home -v 17)
```

## 📦 Deployment

### Run JAR directly:
```bash
java -jar target/kaiburr-task1-0.0.1-SNAPSHOT.jar
```

### Docker Deployment:
```dockerfile
FROM openjdk:17-jdk-slim
COPY target/kaiburr-task1-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app.jar"]
```

## 📝 API Response Format

**Success Response:**
```json
{
  "id": "650a1b2c3d4e5f6a7b8c9d0e",
  "name": "Task Name",
  "assignee": "Assignee Name",
  "project": "Project Name",
  "startTime": "2025-10-20"
}
```

**Error Response:**
```json
{
  "timestamp": "2025-10-20T13:05:44.567+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/api/invalid-endpoint"
}
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

**Note**: Make sure MongoDB is running before starting the application. The API uses MongoDB to store all task data.
```
