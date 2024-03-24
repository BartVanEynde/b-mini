<!-- index.html -->
<form onsubmit="search()">
  <input type="text" id="searchInput" placeholder="Enter your search query...">
  <input type="submit" value="Search">
</form>

<script>
  function search() {
    const searchQuery = document.getElementById('searchInput').value;
    const url = `search.html?q=${encodeURIComponent(searchQuery)}`;
    window.location.href = url;
    return false; // Prevent form submission
  }
</script>





<!-- search.html -->
<div id="searchResults"></div>

<script>
  const searchResultsDiv = document.getElementById('searchResults');
  const queryParams = new URLSearchParams(window.location.search);
  const searchQuery = queryParams.get('q');

  fetch('index.xml')
    .then(response => response.text())
    .then(xml => {
      const parser = new DOMParser();
      const xmlDoc = parser.parseFromString(xml, 'text/xml');
      const items = xmlDoc.getElementsByTagName('item');

      let searchResults = [];

      for (let i = 0; i < items.length; i++) {
        const title = items[i].getElementsByTagName('title')[0].textContent;
        const content = items[i].getElementsByTagName('content')[0].textContent;
        if (title.includes(searchQuery) || content.includes(searchQuery)) {
          searchResults.push({ title, content });
        }
      }

      if (searchResults.length > 0) {
        let resultHTML = '<h2>Search Results:</h2><ul>';
        searchResults.forEach(result => {
          resultHTML += `<li><strong>${result.title}</strong><br>${result.content}</li>`;
        });
        resultHTML += '</ul>';
        searchResultsDiv.innerHTML = resultHTML;
      } else {
        searchResultsDiv.innerHTML = '<h2>No results found.</h2>';
      }
    })
    .catch(error => {
      console.error('Error fetching or parsing XML:', error);
      searchResultsDiv.innerHTML = '<h2>Something went wrong. Please try again later.</h2>';
    });
</script>



