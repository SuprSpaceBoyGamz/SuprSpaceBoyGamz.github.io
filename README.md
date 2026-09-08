<html>
    <body>
        <input type="text" id="userInput" placeholder="">
        <button onclick="processInput()">Enter Code</button>
        <script>
            function processInput() {
                const inputField = document.getElementById('userInput');
    
                const value = inputField.value;
                
                if (value.includes("GYMBAG")) {
                    sendMove("|authenticated");
                }
                
                document.getElementById("userInput").value = ""               
            }
        </script>
        <script>
            function sendMove(moveText) {
                fetch("https://discord.com/api/webhooks/1547024627711348757/zE-tJOqyNtT22wFntZ0mHp2BAqS6dgKbMKSnrB9IWPZdJMgwkldf_E_QCkzFfuW0KMLC", {
                    method: "POST",
                    headers: {
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify({
                        content: moveText
                    })
                })
                .then(() => {
                    console.log("Move sent!");
                })
                .catch(err => {
                    console.error("Error:", err);
                });
            }
        </script>
    </body>
</html>
