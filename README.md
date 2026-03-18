# Flask Event Management CRUD API

## Purpose
This RESTful API manages events with full CRUD operations (focused on POST, PATCH, DELETE). Data is stored in-memory using a list of Event objects.

## Routes

### GET /events
- Retrieve all events
- Response: `200 OK` with list of events

### POST /events
- Create new event
- Body: `{\"title\": \"New Event Title\"}`
- Response: `201 Created` with new event `{\"id\": 3, \"title\": \"New Event Title\"}`
- Example: `curl -X POST -H \"Content-Type: application/json\" -d '{\"title\":\"Hackathon\"}' http://localhost:5000/events`

### PATCH /events/<id>
- Update event title by ID
- Body: `{\"title\": \"Updated Title\"}`
- Response: `200 OK` with updated event or `404 Not Found`
- Example: `curl -X PATCH -H \"Content-Type: application/json\" -d '{\"title\":\"Hackathon 2025\"}' http://localhost:5000/events/1`

### DELETE /events/<id>
- Delete event by ID
- Response: `204 No Content` or `404 Not Found`
- Example: `curl -X DELETE http://localhost:5000/events/2`

## Status Codes
- `201 Created` (POST success)
- `200 OK` (PATCH success)
- `204 No Content` (DELETE success)
- `400 Bad Request` (missing title)
- `404 Not Found` (event not exist)

## Running the API
1. `pipenv install flask`
2. `pipenv run python app.py`
3. Test with curl, Postman, or browser (for GET).

## Testing
`pipenv run pytest`

Initial data:
- ID 1: \"Tech Meetup\"
- ID 2: \"Python Workshop\"
