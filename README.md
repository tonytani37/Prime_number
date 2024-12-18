# Prime_number

ここではみんなが大好きな数字が、素数かそうではないかを判定するサービスをHTMLとJavascriptで書いてみたものです。

ただし、コードはCopilotが教えてくれたものをちょっとだけ手直しをしただけで、一から書いたものではありません。

~~~
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>素数判定</title>
</head>
<body>
    <h1>みんな大好き 素数判定プログラム</h1>
    <label for="numberInput">数値を入力してください:</label>
    <input type="number" id="numberInput">
    <button onclick="checkPrime()">判定</button>
    <p id="result"></p>

    <script>
        function checkPrime() {
            const number = parseInt(document.getElementById('numberInput').value);
            const resultElement = document.getElementById('result');

            if (isNaN(number) || number < 2) {
                resultElement.textContent = '2以上の整数を入力してください。';
                return;
            }

            let isPrime = true;
            for (let i = 2; i <= Math.sqrt(number); i++) {
                if (number % i === 0) {
                    isPrime = false;
                    large_n = number / i;
                    break;
                }
            }

            if (isPrime) {
                resultElement.textContent = `${number} は素数です。`;
            } else {
                resultElement.textContent = `${number} は ${large_n} で割り切れるため素数ではありません。`;
            }
        }
    </script>

</body>
</html>
~~~
