- 👋 Hi, I’m @erikschen
- 👀 I’m Swg .?ljfp98i...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
require('dotenv').config(); // This loads environment variables from a .env file during development
const axios = require('axios');

const token = process.env["GITHUB_TOKEN"];

if (!token) {
  console.error("GITHUB_TOKEN is not set in the environment variables.");
  process.exit(1);
}

// Example: Fetch a list of repositories for the authenticated user
(async () => {
  try {
    const response = await axios.get('https://api.github.com/user/repos', {
      headers: {
        Authorization: `Bearer ${token}`
      }
    });

    console.log(response.data);
  } catch (error) {
    console.error("Error fetching repositories:", error.message);
  }
})();
