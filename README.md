

<!-- ![Image](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExdWd3MTZtNXA4YW1oZ3F2ZTdoNHJueDF3b2J5czYydjF4a2FyaXRraSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/SUPjsJSPpXloyRJSeW/giphy.gif) -->
<!--This famous gesture represents the creation of the first man with the Creator's index finger ready to strike a spark upon contact with Adam's hand. -->


### Hello there

I'm Siddharth K,I'm interested all about data and machine learning systems

Check out my [portfolio](https://github.com/zenvall/My-portfolios)
which includes my macro and micro projects and Certifications.



# GitHub Activity

```javascript
const username = "zenvall";
const repo = "My-portfolios";
const apiUrl = `https://api.github.com/repos/${username}/${repo}/events`;

fetch(apiUrl)
    .then(response => response.json())
    .then(data => {
        data.forEach(event => {
            const eventType = event.type;
            const createdAt = new Date(event.created_at).toLocaleString();
            let activityText = "";
            switch (eventType) {
                case "PushEvent":
                    activityText = `${event.actor.login} pushed to ${event.payload.ref} at ${createdAt}`;
                    break;
                case "PullRequestEvent":
                    activityText = `${event.actor.login} ${event.payload.action} a pull request at ${createdAt}`;
                    break;
                // Add more cases for other event types as needed
                default:
                    activityText = `${event.actor.login} did something at ${createdAt}`;
            }
            console.log(activityText);
        });
    })
    .catch(error => {
        console.error("Error fetching GitHub activity:", error);
    });
