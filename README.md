# Self-Chess-game

## <a href="https://kimssumin.github.io/Self-Chess-game/public/index.html">๐ฎ [Click] Let's play chess game!</a>
## Browser support

<img src="https://img.shields.io/badge/Chrome-4285F4?style=flat-square&logo=Google Chrome&logoColor=white" width="100" height="32"/> <img src="https://img.shields.io/badge/Microsoft Edge-0078D7?style=flat-square&logo=Microsoft Edge&logoColor=white" width="150" height="32"/> <img src="https://img.shields.io/badge/Firefox-FF7139?style=flat-square&logo=Firefox&logoColor=white" width="100" height="32"/>

## Directory Structure

<details open="true">
  <summary>Click to toggle</summary>
  <pre>๐ฆ /
โฃ ๐public
โ โฃ ๐index.html
โ โ ๐style.css
โฃ ๐src
โ โฃ ๐bishop.js
โ โฃ ๐board.js
โ โฃ ๐knight.js
โ โฃ ๐pawn.js
โ โฃ ๐queen.js
โ โฃ ๐rook.js
โ โฃ ๐score.js
โ โ ๐main.js
โฃ ๐package-lock.json
โฃ ๐package.json
โ ๐README.md</pre>
</details>

## Function Structure

**`board.js`**

- board_init โ ๋ฌด์กฐ๊ฑด ์ด๊ธฐํํ๋ ํจ์
- program class
    - constructor ์์ ๋ณ๊ฒฝํ  boards (์ด๊ธฐ๊ฐ์ board_init), ๋ง์ด ํฐ์์ธ์ง ๊ฒ์์์ธ์ง ํ์ธํ  ๋ฐฐ์ด ๋ฃ์ด์ค
    - board_put (type, position, color) โ initPiece์ setPiece ์ ์ฌ์ฉ๋ ํจ์
        - initPiece ๋ ๋ ์ ์๋ ์๊น์ด ์ ํด์ ธ์์ด์ โnoneโ ์ผ๋ก
        - setPiece ๋ ์์ ์ง์ ํ  ์ ์๊ฒ
    - initPiece(type, position) - ์ด๊ธฐํ๋ ์๋ฆฌ์ ์๋ ๋ง์ด ์์ด์ผ๋๋๋ฐ ๋น์นธ์ด ๋ค์ด๊ฐ์๋ ๊ฒฝ์ฐ ๊ทธ ์๋ฆฌ์ ์ฑ์๋๋ ์ฉ๋๋ผ๊ณ  ์๊ฐํจ
    - setPiece (type, position, color) - ๋น์ด์์๋๋ง ์ํ๋ piece๋ฅผ ๋ ์ ์๋๋ก
    - display() - ์ ์ฅ๋ boards๋ฅผ return
    - move(from, to, color) - color ๊ฐ์ ๊ธฐ์ค์ผ๋ก ์ผ๋จ ๋๋ ํ, ๊ฐ๊ฐ์ ๊ฒ์์ ์ธ ์ผ์ด์ค๋ก ๋๋ ์ ์์(์ด๋ํ๋ ค๋ ๊ณณ์ด ๋น ๊ณต๊ฐ์ธ ๊ฒฝ์ฐ, ๊ฐ์์ ๋ง์ด ์๋ ๊ฒฝ์ฐ, ๋ค๋ฅธ ์ ๋ง์ด ์๋ ๊ฒฝ์ฐ)
        - ์ด๋ ๋ค๋ฅธ์ ๋ง์ด ์๋ ๊ฒฝ์ฐ score() ๋ฅผ ํธ์ถํด์ score ๊ณ์ฐํ ํ ์ถ๋ ฅ๋๋๋ก ์์ฑ
    - chess_what(position) - ๊ฐ position ๋ณ๋ก ๊ทธ ์์น์ ๋์ธ ๋ง์ด ๋ฌด์์ธ์ง ํ๋จํ ํ, ์ด๋๊ฐ๋ฅํ ๊ณณ๋ค์ ๋ํ ์ ๋ณด๋ฅผ return
    - chess_next (position, next) - ์ฌ๊ธฐ์ next ๋ program.js ์์ ๋ฐ์์ค๋ ๋ณ์๋ก, ํ์ฌ ๋ฐฑ์ ๋ง์ ํด์ธ์ง ํ์ ๋ง์ ํด์ธ์ง๋ฅผ ์๊ฒํด์ค
        - ์ด next ๋ฅผ ๊ธฐ์ค์ผ๋ก ์ง๊ธ ๋ค์ด์จ ์์น์ ๋ง์ด ์ง๊ธ ํด ์์ ๋ง์ด ๋ง๋์ง check ํด์ฃผ๋ ํจ์

**`rook.js ์ธ ๊ฐ ๋ง์ js ํ์ผ`**

- position ์ ๋ํ ํจ์๋ฅผ ๋ฐ๋ก ์์ฑํ์ฌ A1 ์ฒ๋ผ ๋ฌธ์์ด๋ก ๋ค์ด์จ ์์น์ ๋ณด๋ฅผ 2์ฐจ์ ๋ฐฐ์ด์ index๋ก ๋ณ๊ฒฝ
- possiblePositions_(โ๋ง์ typeโ) - ํธ(8๋ฒ)๊ณผ ํฐ(1๋ฒ)์ ์ ์ธํ๊ณ ๋ ์์ง์ผ ์ ์๋ ๋ฐฉํฅ์ ๊ฐฏ์๊ฐ 4๊ฐ๋ผ์ ๋ฐ๋ณต๋ฌธ์ 4๋ฒ ๋๋๋ก ํ์๊ณ , ์ฒด์คํ์ ๋ฒ์ด๋์ง ์๋ ์ ์์ ์์ง์ผ ์ ์๋ ๋ชจ๋  ๊ฒฝ์ฐ์ ์๋ฅผ str์ pushํด ์ต์ข์ ์ผ๋ก return

**`score.js`**

- check ํจ์๋ฅผ ํตํด ๋ค์ด์จ ๋ง์ด ๋ช ์ ์ง๋ฆฌ ๋ง์ธ์ง check
- score_total ์๋ scores ๋ผ๋ ๊ฐ์ฒด๋ฅผ ๋ฃ์ด๋๋๋ฐ, ์ด black ๊ณผ white๋ฅผ ํค ์ผ์์ ์ ์๋ฅผ ๋ํ๋ ์
    - ์ ์๋ฅผ ์ฐ์ ํ ๋๋ ๋ฌธ์ ์์ ํ์ฌ ๋์ฌ์๋ ๋ง์ ์ ์๋ผ๊ณ  ์ ํ์์ผ๋ฏ๋ก ์ฒด์คํ์์ ์กด์ฌํ๋ ๊ฐ ๋ง์ ์ ์ ํฉ์ ๊ตฌํจ
