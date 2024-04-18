<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="JavaScript" alt="JavaScript" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/java/java-original-wordmark.svg" title="Java" alt="Java" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" title="React" alt="React" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original.svg" title="React Native" alt="React Native" width="40" height="40"/>&nbsp;
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/laravel/laravel-original-wordmark.svg" title="Laravel" alt="Laravel" width="40" height="40" />
  <img src="https://github.com/devicons/devicon/blob/master/icons/php/php-original-wordmark.svg" title="PHP" alt="PHP" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/firebase/firebase-plain-wordmark.svg" title="Firebase" alt="Firebase" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/mysql/mysql-original-wordmark.svg" title="MySQL"  alt="MySQL" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original-wordmark.svg" title="Git" alt="Git" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/python/python-original.svg" title="Python" alt="Python" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/c/c-original.svg" title="C" alt="C" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/cpp/cpp-original.svg" title="C++" alt="C++" width="40" height="40"/>&nbsp;
</div>

<script>
  // Counts for each language
  const counts = {
    "JavaScript": 1000,
    "Java": 800,
    "React": 600,
    "React Native": 500,
    "Laravel": 400,
    "PHP": 300,
    "Firebase": 200,
    "MySQL": 100,
    "Git": 50,
    "Python": 700,
    "C": 400,
    "C++": 300
  };

  // Calculate total count
  const totalCount = Object.values(counts).reduce((acc, curr) => acc + curr, 0);

  // Calculate percentages
  const percentages = {};
  for (const [lang, count] of Object.entries(counts)) {
    percentages[lang] = (count / totalCount) * 100;
  }

  // Sort languages by percentage
  const sortedLanguages = Object.keys(percentages).sort((a, b) => percentages[b] - percentages[a]);

  // Display rank
  sortedLanguages.forEach((lang, index) => {
    const percentage = percentages[lang].toFixed(2);
    console.log(`${index + 1}. ${lang}: ${percentage}%`);
  });
</script>


