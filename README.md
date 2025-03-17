<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reliance Live LTP</title>
    <script>
        async function fetchLTP() {
            const url = "https://api.fyers.in/api/v2/quotes/1.0/NSE:RELIANCE-EQ";
            const token = "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJhcGkuZnllcnMuaW4iLCJpYXQiOjE3NDIxODg1NjUsImV4cCI6MTc0MjI1NzgwNSwibmJmIjoxNzQyMTg4NTY1LCJhdWQiOlsieDowIiwieDoxIiwieDoyIiwiZDoxIiwiZDoyIiwieDoxIiwieDowIiwieDoxIiwieDowIl0sInN1YiI6ImFjY2Vzc190b2tlbiIsImF0X2hhc2giOiJnQUFBQUFCbjE3QVZvSDNFZi1RMEFaUmt0TDYxSWZDa0hySVA0em11ZzFmQXNzWi1vb2xHOXUtUE9oRVF3M3FHQ0xzYk5nLVZCeE5PZHV6SzN2WWlRanY4cE1ZN0lIZll2VHlLTU5JNkNxRzlOZ1hWUHI2WlZjST0iLCJkaXNwbGF5X25hbWUiOiJNQURIVVNPT0RIQU5BTiBOQUlSIEsiLCJvbXMiOiJLMSIsImhzbV9rZXkiOiI5YWVkZDQ2MDQ5OGJmZjFlZmIzN2YzZDhlZDNkM2NmYmNmOWIzZjQxZDhiZmY0M2M0ZjcxZjYxZSIsImlzRGRwaUVuYWJsZWQiOiJOIiwiaXNNdGZFbmFibGVkIjoiTiIsImZ5X2lkIjoiWU0yOTE2OSIsImFwcFR5cGUiOjEwMCwicG9hX2ZsYWciOiJOIn0.VCo58vd1UzZtdRhJ4GH_71L3Z-b4K6_SnvioAkitgNY"; // Replace with your Fyers API Token

            try {
                let response = await fetch(url, {
                    method: "GET",
                    headers: {
                        "Authorization": "Bearer " + token
                    }
                });
                let data = await response.json();
                document.getElementById("ltp").innerText = "Reliance LTP: ₹" + data.d[0].ltp;
            } catch (error) {
                console.error("Error fetching LTP:", error);
                document.getElementById("ltp").innerText = "Error fetching data";
            }
        }
        setInterval(fetchLTP, 5000); // Update every 5 seconds
    </script>
</head>
<body onload="fetchLTP()">
    <h2 id="ltp">Fetching LTP...</h2>
</body>
</html>
