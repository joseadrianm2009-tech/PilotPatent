function doGet() {
  return HtmlService.createHtmlOutputFromFile('index');
}

function getPatents() {
  const sheet = SpreadsheetApp.openByUrl("https://docs.google.com/spreadsheets/d/1YW02ae_sXKiwRgRqUhDo8GdScXvv4NTh9JkLQpj-9wc/edit?gid=0#gid=0").getActiveSheet();
  const data = sheet.getDataRange().getValues();

  let patents = [];

  for (let i = 1; i < data.length; i++) {
    patents.push({
      title: data[i][0] || "",
      abstract: data[i][1] || "",
      link: data[i][2] || ""
    });
  }

  return patents;
}
  <script src="script.js"></script>
</body>
</html>
