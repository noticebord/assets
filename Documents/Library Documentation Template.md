# Library Documentation Template

# Installation

To install, run the following command


```bash
	install this package
```

Or add the package to your `packages.html` file:

```html
	<ul>
		...
		<li>this package</li>
	</ul>
```

# Usage 

## NoticebordClient

This is the entry point to the SDK:

```ts
	const client = new NoticebordClient();
```

Providing a valid access token will allow you tyo perform action on behalf of users:

```ts
	const client = new NoticebordClient(token);
```

You can also provide a custom base URL to connect to an instance of the web platform hosted elsewhere:

```ts
	const client = new NoticebordClient(token, baseUrl);
```

## Tokens

A token is needed to access restricted endpoints and perform actions on behalf of users.

### Get a Token

Create a request object:

```ts
	const request = {}
```

Use your request object to get a token from the server;


```ts
	const token = await NoticebordClient.getToken(request);
```

You can optionally provide a custom base url:

```ts
	const token = await NoticebordClient.getToken(request, baseUrl);
```

You can now create a Noticebord client with your token.

## Notices

### Service

An instance of the notice service can be obtained from the Noticebord client.
```ts
	const service = client.notices
```

### Creating a notice

```ts
	const request = {}
	const notice = await service.createNotice(request);
```

### Fetching notices

```ts
	const notices = await service.fetchNotices();
```

> This endpoint is cursor paginated, and you can optionally include a cursor to fetch results from a specific page.


```ts
	const notices = await service.fetchNotices(cursor);
```

### Fetching a single notice

```ts
	const notices = await service.fetchNotice(noticeId);
```

### Updating notices

```ts
	const request = {}
	const notice = await service.updateNotice(request);
```

### Deleting notices

```ts
	await service.deleteNotice(noticeId);
```

## Team Notices

### Service

An instance of the team notice service can be obtained from the Noticebord client.
```ts
	const service = client.teamNotices
```

### Creating a team notice

```ts
	const request = {}
	const teamNotice = await service.createTeamNotice(teamId, request);
```

### Fetching team notices

```ts
	const teamNotices = await service.fetchTeamNotices(teamId);
```

This endpoint is cursor paginated, and you can include a cursor, to fetch results from a specific page.


```ts
	const teamNotices = await service.fetchTeamNotices(teamId, cursor);
```

### Fetching a single team notice

```ts
	const teamNotice = await service.fetchTeamNotice(teamId, teamNoticeId);
```

### Updating team notices

```ts
	const request = {}
	const teamNotice = await service.updateTeamNotice(teamId, request);
```

### Deleting team notices

```ts
	await service.deleteTeamNotice(teamId, teamNoticeId);
```

## Topics

### Service

An instance of the topic service can be obtained from the Noticebord client.
```ts
	const service = client.topics
```

### Fetching topics

```ts
	const topics = await service.fetchTopics();
```

### Fetching a single topic

```ts
	const topic = await service.fetchTopic(topicId);
```

### Fetching topic notices

```ts
	const notices = await service.fetchTopicNotices(topicId);
```

This endpoint is cursor paginated, and you can include a cursor, to fetch results from a specific page.


```ts
	const notices = await service.fetchTeamNotices(topicId, cursor);
```

## Teams

### Service

An instance of the team service can be obtained from the Noticebord client.
```ts
	const service = client.teams
```

### Fetching teams

```ts
	const teams = await service.fetchTeams();
```

### Fetching a single team

```ts
	const team = await service.fetchTeam(teamId);
```

## Users

### Service

An instance of the user service can be obtained from the Noticebord client.
```ts
	const service = client.users
```

### Fetching users

```ts
	const users = await service.fetchUsers();
```

### Fetching a single user

```ts
	const user = await service.fetchUser(userId);
```

### Fetching the current user

```ts
	const user = await service.fetchCurrentUser();
```

### Fetching user notices

```ts
	const notices = await service.fetchUsersNotices(UserId);
```

## Fetching user notes (Private notices)

```ts
	const notes = await service.fetchUserNotes(userId);
```

# Building From Source

## 0. Prerequisites

- Git

## 1. Clone the repo from GitHub

```bash
	git clone https://github.com/noticebord/client-{platform}
```

## 2. Build the project

```bash
	builder build project
```

## 3. Running Tests

```bash
	tester test project
```

# Contributing

Thiss project is governed by the [Noticebord contribution guidelines](#).