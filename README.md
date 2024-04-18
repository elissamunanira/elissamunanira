<div id="languages">
  <!-- Language icons will be dynamically added here -->
</div>

<script>
  // Function to fetch repository data from GitHub API
  async function fetchRepoData(language) {
    const response = await fetch(`https://api.github.com/search/repositories?q=language:${language}`);
    const data = await response.json();
    return data.total_count;
  }

  // List of languages
  const languages = ["JavaScript", "Java", "React", "React Native", "Laravel", "PHP", "Firebase", "MySQL", "Git", "Python", "C", "C++", "Node.js"];

  // Fetch repository data for each language and calculate total count
  Promise.all(languages.map(language => fetchRepoData(language)))
    .then(repoCounts => {
      const totalCount = repoCounts.reduce((acc, curr) => acc + curr, 0);

      // Calculate percentages
      const percentages = {};
      languages.forEach((language, index) => {
        percentages[language] = (repoCounts[index] / totalCount) * 100;
      });

      // Sort languages by percentage
      const sortedLanguages = languages.sort((a, b) => percentages[b] - percentages[a]);

      // Display rank
      sortedLanguages.forEach((language, index) => {
        const percentage = percentages[language].toFixed(2);
        const rank = index + 1;
        console.log(`${rank}. ${language}: ${percentage}%`);
        // Append language icons to the HTML
        document.getElementById('languages').innerHTML += `
          <img src="https://github.com/devicons/devicon/blob/master/icons/${language.toLowerCase()}/${language.toLowerCase()}-original.svg" title="${language}" alt="${language}" width="40" height="40"/>&nbsp;
        `;
      });
    })
    .catch(error => console.error(error));
</script>
