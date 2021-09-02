## Project Status
![Generic badge](https://img.shields.io/badge/build-passing-green.svg)
<br/> [Check out the actual website!](https://github.com/beegramin9/HCJ-Nomad-CalculatorClone) try!

## Overview
![Calculator](https://user-images.githubusercontent.com/58083434/130403502-8078a35a-2760-42a9-8d03-80bf0aa56aeb.gif)

## Technology Stack
<img src="https://img.shields.io/badge/Javascript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=white"/></a>&nbsp;
<img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=HTML5&logoColor=white"/></a>&nbsp;
<img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=CSS3&logoColor=white"/></a>

## Outline
&nbsp;The calculator functionality is pulled through by Javascript ES6 Class, which made easier to store and call the values and operator functions the separately. The number blocks and button blocks are constructed within CSS3 grid, flex, which made easier to remain intact when the web moves responsively. Built reponsive with @media, covers all design with pure CSS3, no other framework such as Bootstrap used.
<br/><br/>
&nbsp;기본적인 계산기 기능에 반응형 디자인을 더했습니다. Javascript ES6에 추가된 클래스를 이용하여 계산기 기능들을 구현했습니다. 컴퓨터공학 전공생들이면 누구나 하는 기본적인 프로젝트이지만, css 디자인을 통해 사용자들에게 더 매력적으로 다가올 수 있게 만들었습니다.

## Main Feature Code
- Building Calculator <br/>
> (/index.html) <br/>
> data-type property로 operator, reset, equal 버튼을 구별합니다. 기본값 number <br/>
```html
<section class="calculator">
    <input type="text" id="result" value="0" disabled>
    <button data-type="reset" class="button" id="reset"  value="C">C</button>
    <button class="button" value="7">7</button>
    <button class="button" value="8">8</button>
    <button class="button" value="9">9</button>
    <button data-type="operator" class="button color-inversion" value="+">+</button>
    <button class="button" value="4">4</button>
    <button class="button" value="5">5</button>
    <button class="button" value="6">6</button>
    <button data-type="operator" class="button color-inversion" value="-">-</button>
    <button class="button" value="1">1</button>
    <button class="button" value="2">2</button>
    <button class="button" value="3">3</button>
    <button data-type="operator" class="button color-inversion" value="*">*</button>
    <button class="button" id="zero"  value="0">0</button>
    <button data-type="equal" class="button" id="equal" value="=">=</button>
    <button data-type="operator" class="button color-inversion" value="/">/</button>
</section>
```

- Grid로 계산기 디자인 <br/>
> (/style.css) <br/>
> grid-template-columns: repeat(4, 1fr); 으로 4열 계산기를 디자인합니다. <br/>
```css
.calculator {
  margin-top: 30px;
  position: relative;
  background-color: transparent;
  display: grid;
  width: 400px;
  grid-template-columns: repeat(4, 1fr);
  justify-content: center;
  text-align: center;
  font-size: 3em;
  grid-gap: 0.25em;
}
```

- switch문 <br/>
> (/main.py) <br/>
> switch문으로 operator, reset, equal, number 버튼을 구별합니다. <br/>
```js
buttons.forEach(button => {
    button.addEventListener('click', () => {
        switch (button.dataset.type) {
            case 'operator':
                console.log('operator');
                if ( calculator.appendOperator(button.innerText) ) {
                    calculator.updateDisplay()
                }
                break
            case 'reset':
                console.log('reset');
                calculator.reset();
                break
            case 'equal':
                console.log('equal');
                calculator.compute();
                calculator.updateDisplay();
                break
            default:
                console.log('number');
                calculator.appendNumber(button.innerText)
                calculator.updateDisplay()
                break
        }
    }
)})
```
