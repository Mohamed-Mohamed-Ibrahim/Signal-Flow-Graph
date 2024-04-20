<template>
    <div class = "navbar">
        <div class = "items">
          <button class = "btn btn-outline-dark" @click  = "addNode">  <img src="data:image/png;base64,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"></button>
          <button class = "btn btn-outline-dark" @click  = "join">     <img src="data:image/png;base64,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"></button>
          <button class = "btn btn-outline-dark" @click  = "input">    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAD/ElEQVR4nO1YS4gdRRQtMf7AQY3GPxhBXfiJoqJkIWIkiSiu/IFGhYgoDCiBZARFH4jvdd9zqmbeyCzyEL+o4OhSib8sjC4DMdk4EUSIkqzEz6gLE5xwxiroNG9mMqT7zTx8Bwqqq+rePre66tapdm6AAZYvzOxKFdevAPAYyUeXmsf/FySfAzDi+hUTExNnqrh+Bcl1Kq5fQXKdmd3h+hUkL1Nx/QoAHRXXr8AggCUAgAtDCNeXl5Da1OeWIxqNxukknya5F8C/AEbLAagt9n0L4Knx8fHT3HIAgAdIHiL5E4Ct3vur5trE6iO5DcDPAA4CuG/JiGsGAbwF4G/v/bONRuNUtc/MzJyUgigGIFWqvmRLcotsAbzR868RCXxCcirP82vURvJ8yYYsy1aT3FUOQG06E8xsSGNj27UkvwfwcU+DIDkJYP/o6OhFqQ3/4eGF0qj3/hENTM9mdnEM4oOekAfwJMnfNNORwOYQwhWLPchkY2abVSd5OYDfST5RK/lms7kKwJ/FS4rqIrDYAGTDY/08TvIP7/15NdGfJdQEsFv1PM8v9d5vPFEpAeAuBaMNTnIPyZddHVCWAfCr0qaevfc3ARiuIIBhM7tRdTN7CMAvnU7nlIrpzzq/neRfOrT0nFJiFWJuJvoKIZyh1Gpmt7mqQfIVkjti/UHl7/KYVqt1bgqwWwDq05guvt+Uz1j/rJZlBOB9koxEViifdyHykYJMQRQDiHJjh8aU7cxsaHJy8uToI5B8r44AdkoGxJfcGkJY2YWIcvpUCiIFUCA/pTFluxDCSvmM7xkB8GXlAZD8huQz8SXNPM9v6TauGATJt2OZk7wg8lqiqkuWAPjaVQ0AH5LMjmdsCgLAEZX5yJcBINdJ76oGyVcBvKO6skRaTnOh8CUWJE9yW8o8AN4F0K6Y/qzjTQAOKOWFEC4BsHYhGxE/npkHsFY+5TtK7WM0VSXIsuwcAP+Y2c2R3FAVP26zLFudMpr2ld4xNjZ2tqsD2owAXlMdwAaSYyfqE0Dbe78++n9d0trVBc0QycMkr05tOphSDl8MZNMqHGrxbnA4feG67wJfJb2ig8l7f+di/ciG8VCTL6VOHZaubkhSk/yR5PYSoY3pb8R8AHADyXtLbR0AP3STGbUghHAdgGmt37R8pFK1xPI8P0t/HdSmzZn+TqtNfXEZ3p8kCYBx3QO0hFwvITkd/0R8WkyVmkUAL0bSIwX58VJxhmMq/lypOcnpnkN3YukWyWzJCy2vhWx0oQfQkg3JL9rt9gW9YTs/qXsA7IuyYZeZPa/Lu+4QKvEi/4L64pi9Zna3W24AsEbLR8oVwHdxn0zH+s7Yt2apeQ4wwAADuMpwFOQd9z4/xHFhAAAAAElFTkSuQmCC"></button>
          <button class = "btn btn-outline-dark" @click  = "output">   <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAD/ElEQVR4nO1ZTYhcRRBu8TdgUBONfwEjGA9GoyTGJQfxIBpRPGkU1BhICBECimAiKOZBcGZefV/37KzsIaP4g6jgmqPibw7GHAWNF39ABA16khiTeDDiyhe79e2yuzNL3pudgfngQXV1V01Vd73qqjfODTFE/4LkOj1uEGFmawD8SvI3kiNukEByHYAjxWdgTsL+3/lA8kUAbQC1gTgJi8YDaGocjW9Hut73TgB4DYAvjP9zII691rh+RZZlZxXH0x2YaU1fYyYHBgoYOrDAGMgTAHBZCOHG6Q6IpznXj8iy7DySj5E8BODvWe6BZpz7EsD2sbGxc10/AMBGkr+Q/AnAU977a2cLIc2R3AngMICfAdy3YIZrB+PF9Yf3/oksy84Rf3Jy8ozkRNEBM1upuSRL8knJAnil56cRDXiP5Dd5nq8Sj+Sy8fHx8xuNxgqSB6Y7IB7Jq8xssdZG3vUkvwPwbk+dIDkB4Ntms3l54uFfPNQpC3nvH9bCNDazK6ITb/fEeADbVJRpp6MBW0II18w3jUrGzLaIJnk1gKMkt1ZqfK1WuwTAcZKbEk+0DJivA5LhVD2bSf7uvb+4IvNPGVQD8LnoPM+Xe+83nO5FBuAuOaMXnOQXJPe4KqAsE7urjRp779cC2FGCAzvUR4g2swfVT7Tb7bNLNv+U8ttIntClpXFKiWVgMuoKISxSajWzW13ZIPk8yfcj/YDydxcymwE82sW6V6Uz0h9WEkYA3iLJ1JQon3eSUaaZLUMVYWaLJyYmzhQde+k3XdkAsF9lQPyRkRDCki4MW6mn07oQwpLUKwPYBeATVzZIHiT5ePyRWp7nt3SSUfgUU+UcukcUoqJVlgD4rCSzpxjzDsmGqxgkrZJbmeQLAF4XrSyRwqmDzNMKiS7W7UyZB8AbAFqubAB4BMCPSnkhhCsBrO8ko+JOTxe610undMdSe0pNVQoajcZFAP40s5tT5ujmBe1C74qU0fRe6TdGR0cvdFVA9wCAl0QDuJPk6OnqBNDy3t8R9b+s0tpVBe0QyZMkr0u8er2+NOXw+UAy9Xp9aRrH3uBkOuGqe4FPU71Ccp/3/vb56pEMyX2ipUupU5elqxoqqUn+QHLvNIM2pK8RcwHATSTvnaHo+754IpUihHADgGOK3xQ+qlIVYnmeX6CvDuLp5UxZSDzNxTC8P5UkAMbUByiEXC+hcjp+ifhAbWHiaxcBPBeN3lUoP3YXdzim4o+UmlM53XOoJ1bdojJb5YXCq5OMGvr4X8EJkh+3Wq1Le2Pt3EbdA+ArAH/p64OZPaPmXT2EntjIP6u5uOaQmd3t+g0AVit8VLkC+Dq+J8civT/OrV5oO4cYYoghXGn4Bzhh6tvikfPCAAAAAElFTkSuQmCC"></button>
          <button class = "btn btn-outline-dark" @click  = "gain">     <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAACXBIWXMAAAsTAAALEwEAmpwYAAAFIUlEQVR4nO1YCYhWVRi9Ypntu62002obBWkbFkW2EZq0ZxFtkCWlQWV0I5j53z3nvn/mr0kdWmjTYpiKosIWi7IaigrbC8oWMNP2bDOpP07zPXk8RkanmekN/Ad+5nHv481dvu+c833ONdBAAw0MOXR0dAwnOTHGeKSe3VADgITkjwB+I/kBgLFuKIHkqySvSpJkUwDtAP4EcE29Xh/myg6Su5J8CcDtWjCAOwG8a7dxr/d+hCsrQgiHAngHwHUAfiL5tP4COCBN0zEklwF4xnu/gSsjSF4N4G49A3iO5EdJkuyYzQPYneQnJJ9N03R9VzbEGA+xUNm3Wq3uZqd/ev6dJEl2AvApgHne+5GubCDZBuDzarW6HcmzAPxQqVR2KbyzM8nPSD5Zupzw3o8g+TLJN8VCJGeKldrb29fN3gGwLcnvAfxCsrN0WpGm6RYk3wbQRXIUgNcBzMrN7wHgshjjwST/AnBP6Si2tbV1GwBvaRMhhL0UVjHGqfl3SFYAfKwwU+i5sqFWq21iVNolNSb5LcmTs/kkSfZpaWnZjOQcknWSt7iyoaOjYziAZuVFCOEkAN+QPCybb25u3lJ0K+WWYscYL3VlRAjhGJJBmyC5WGFVfIfkBdpE/pZKCZKTJGghhO2LcwBmiJ0AeLnZPHuVCgAuBLBQVFucIzlbOQHgb9vMYzHGE0rHVCSvB/BCrVZbLz/uvV8HwHyxmMIJwB0kfzVrPt6VATJ4lryLAcwtnq6SG92W41/9EFsBaDJrjj7fhpQ2hHAUyWkhhDNJjl6bOI0xbhVCuME8UyfJDQFUpQnFd0mOJvlzCOGigt/6kuStfdpAfiMkx+lUSD5vavugKFOCBeCcGOPxunJ5IpI3AXiU5O8Srxjj2dm3srqhJwoFcJrCR1Y9rx+iYwDnuf6C4jjGeDjJywG0knwEwCsA3pB9BnCfYl7MohhP03T/vBs1vZgrmi1+m+SNJL9oamraOrex4ySM8lVuMGE2+30tSPVBfi7GuCeApWmaHpgfr9frwxRuSmxtPhu3g+oczPXrn94GIMpm9DD3OMkpKoqKJxtC2BjAh2oYZGMqinQYCjNXBgBYLr5XYku1faHgUaFkpeqJhaRe1NOBDDqs+J+RnTjJKUW6JHmGaut8qWo58t9YqT9A8lQAX2eLS7rbMhNU0cUY9xatWpGUAliQ5YMJX1eSJPv9b4u3BJ5sVCsL/oTZ8PliMWOyhdYwW6C/ee0wuz6zXxaja1fx7gYA3vuRCi2SK6yaW2Ut1Cjo84cl75J/ex6vtoobQJCcZnX1V2ma7mBjc/r8QQDfZT1Qki0SLj23tbVtpARbk8J9TUTJd4vgGAAvknwIwHTrQUntJ63VouVrpKwxxovtOuepVaJEJPmama+nZDV6+5ZoEMAfVqFNBPCAcfxSsY5O234r5KPkUCuVyuZmQ6QfN/e6YJ1mCOEUtQ7tlKsyZtqAeZZjxcskj44xnmstlSXiaQBX9NZStKTVopeTvAvAlZbYag5MkH1QkzhfkuaaZYukH66/odCRcVPPVM6S5P3q1skuqOUif6MNyzaTXGlm76C89SC5rLDRWTq4fHtSNyA9cAMFXbXCzaqtJdaFyH4rLaZ1g1Ota3ctyfPVILOwmSzbbmNLxPnW+Z6uFo5ul+R7GZEMOHTyEic1uaS6+Tn5f9lzdhc7crHjLP7rVpmtSlYAR1i+PKzON4BLXBlR607ysas7YVGp5d2owV9dAw000IBbDf4Byd0EAHxEvB8AAAAASUVORK5CYII="></button>
          <button class = "btn btn-outline-light" @click = "calculate"><img src="data:image/png;base64,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"></button>
          <label for="quantity">Enter the gain:</label>
          <input type="number" id="quantity" name="quantity">
          <button class = "btn btn-outline-success" @click = "read_gain" id = 'readGainButton'>Enter</button>
        </div>
    </div>
    <div id = "container">
    </div>
    <div id = "hiddenDiv">
        <div id="allInfo">
        <button @click="hideDiv()" id="hideCalc">Close</button>

            <div id="toLeftPlease">Paths: </div>
            <div  class="infoContainer" :key="index" v-for="(path,index) in paths">
                {{ "path "+(index+1)+" = "+path }}
            </div>
            <div id="toLeftPlease">Loops: </div>
            <div  class="infoContainer" :key="index" v-for="(loop,index) in loops">
                {{ "loop "+(index+1)+" = "+loop }}
            </div>    
            <div id="toLeftPlease">Non Touching Loops: </div>
            <div  class="infoContainer" :key="index1" v-for="(nonTouchingLoopsList,index1) in nonLoops">
                {{ (index1+2)+" = " }}{{ nonTouchingLoopsList.length != 0 ? nonTouchingLoopsList : "N/A"  }}
            </div>
            <div id="toLeftPlease">Δ: </div>
            <div  class="infoContainer" :key="index" v-for="(triangle,index) in triangles">
                {{ "Δ"+(index == 0 ? "" :index)+" = "+triangle }}
            </div>
            <div id="toLeftPlease">Transfer Function: </div>
            {{ transferFn }}

        </div>
    </div>
</template>

<script>
import Konva from 'konva' ;

export default {

name: 'SystemComponent',
  
  data() {
    return {
        node_id      : 0 ,
        input_id     : 0 ,
        output_id    : 0 ,
        gains        : {},
        curveLineMap : new Map(),
        layer        : new Konva.Layer(),

        graph        : [],

        paths        : [123, 12],
        loops        : ["12", "123", "112"],
        nonLoops     : [],
        triangles    : [1234, 123, 12],
        transferFn   : -1 ,
    };
  },

  methods:{

    addNode() {
        const stage = new Konva.Stage({
            container : 'container',
            width     : window.innerWidth,
            height    : window.innerHeight,
        });

        stage.add(this.layer);

        const circle = new Konva.Circle({
            x         : stage.width() / 2,
            y         : stage.height() / 2,
            id        : String(this.node_id),
            radius    : 35,
            fill      : 'white',
            stroke    : 'black',
            draggable : true,
        });

        this.layer.add(circle);

        // const Node_DTO = {
        //   id : circle.id() 
        // };

        // fetch('http://localhost:8080', {
        //   method: 'POST',
        //   headers: { 'Content-Type': 'application/json' },
        //   body: JSON.stringify(Node_DTO),
        // })
        
        const textInside = new Konva.Text({
            text          : String(this.node_id++),
            fontSize      : 20,
            fill          : 'black',
            align         : 'center',
            verticalAlign : 'middle',
        });

        textInside.position({
            x : circle.x() - 5,
            y : circle.y() - 10,
        });

        this.layer.add(textInside);

        circle.on('dragmove', () => {
            textInside.position({
                x : circle.x() - 5,
                y : circle.y() - 10,
            });

            this.layer.draw();
        });

        this.layer.draw();
    },

    join() {
        const selectedCircles = [];

        const clickHandler = (e) => {
            const shape = e.target;

            if (shape.getClassName() === 'Circle') {
                const currentCircle = shape;
                selectedCircles.push(currentCircle);

                if (selectedCircles.length === 2) {
                    const [startCircle, endCircle] = selectedCircles;
                    this.layer.off('click', clickHandler);

                    const startRadius = startCircle.radius();
                    const endRadius = endCircle.radius();
                    const startPointX = startCircle.x();
                    const startPointY = startCircle.y() - startRadius;
                    const endPointX = endCircle.x();
                    const endPointY = endCircle.y() - endRadius;

                    const controlX = (startPointX + endPointX) / 2;
                    const controlY = (startPointY + endPointY) / 2 - 100;

                    const curveArrow = new Konva.Arrow({
                        stroke: 'darkgrey',
                        strokeWidth: 5,
                        tension: 1,
                        points: [
                            startPointX, startPointY,
                            controlX, controlY,
                            endPointX, endPointY,
                        ],
                        pointerLength: 10,
                        pointerWidth: 10,
                        fill: 'darkgrey',
                    });

                    this.layer.add(curveArrow);
                    curveArrow.moveToBottom();

                    this.curveLineMap.set(`${startCircle.id()}_${endCircle.id()}`, curveArrow);

                    selectedCircles.length = 0;
                }
            }
        };

        this.layer.on('click', clickHandler);

        this.layer.on('dragmove', () => {
            this.curveLineMap.forEach((curveArrow, key) => {
                const [startCircleId, endCircleId] = key.split('_');
                const startCircle = this.layer.findOne(`#${startCircleId}`);
                const endCircle = this.layer.findOne(`#${endCircleId}`);

                const startRadius = startCircle.radius();
                const endRadius = endCircle.radius();
                const startPointX = startCircle.x();
                const startPointY = startCircle.y() - startRadius;
                const endPointX = endCircle.x();
                const endPointY = endCircle.y() - endRadius;

                const controlX = (startPointX + endPointX) / 2;
                const controlY = (startPointY + endPointY) / 2 - 100;

                curveArrow.points([
                    startPointX, startPointY,
                    controlX, controlY,
                    endPointX, endPointY,
                ]);
            });
            this.layer.batchDraw();
        });
    },

    input() {
        let previousInputCircleId = this.input_id;

        const inputClickHandler = (e) => {
            const shape = e.target;

            if (shape.getClassName() === 'Circle') {
                if (previousInputCircleId) {
                    const previousCircle = this.layer.findOne(`#${previousInputCircleId}`);
                    if (previousCircle && previousCircle !== shape) {
                        previousCircle.fill('white');
                    }
                }

                shape.fill('lightgray');
                this.input_id = shape.id();
                previousInputCircleId = shape.id();
                this.layer.batchDraw();
                this.layer.off('click.input', inputClickHandler);
            }
        };

        this.layer.on('click.input', inputClickHandler);
    },

    output() {
        let previousOutputCircleId = this.output_id;

        const outputClickHandler = (e) => {
            const shape = e.target;

            if (shape.getClassName() === 'Circle') {
                if (previousOutputCircleId) {
                    const previousCircle = this.layer.findOne(`#${previousOutputCircleId}`);
                    if (previousCircle && previousCircle !== shape) {
                        previousCircle.fill('white');
                    }
                }

                shape.fill('DarkSlateGray');
                this.output_id = shape.id();
                previousOutputCircleId = shape.id();
                this.layer.batchDraw();
                this.layer.off('click.output', outputClickHandler);
            }
        };

        this.layer.on('click.output', outputClickHandler);
    },

    gain() {
        let selectedCurve = null;
        const curveTextMap = new Map();
        this.gains = {};

        const handleCurveClick = (curve) => {
            if (selectedCurve) {
                selectedCurve.stroke(selectedCurve.originalColor);
            }
            curve.originalColor = curve.stroke();
            curve.stroke('red');
            selectedCurve = curve;
            let curveKey = null;
            this.curveLineMap.forEach((value, key) => {
                if (value._id === curve._id) {
                    curveKey = key;
                    return;
                }
            });

            const boundingBox = curve.getClientRect();
            const curveCenterX = boundingBox.x + boundingBox.width / 2;
            const curveCenterY = boundingBox.y + boundingBox.height / 2;

            let text = curveTextMap.get(curve);
            if (!text) {
                text = new Konva.Text({
                    x: curveCenterX,
                    y: curveCenterY,
                    text: `${document.getElementById('quantity').value}`,
                    fontSize: 16,
                    fontFamily: 'Arial',
                    fill: 'black',
                    align: 'center'
                });

                this.layer.add(text);
                curveTextMap.set(curve, text);
            } else {
                text.text(`${document.getElementById('quantity').value}`);
            }

            if (curveKey) {
                this.gains[`${curveKey}`] = document.getElementById('quantity').value;
            } else {
                console.error('Start or end ID of the curve is undefined.');
            }
        };

        this.layer.on('click', (e) => {
            const shape = e.target;
            if (shape.getClassName() === 'Arrow') {
                handleCurveClick(shape);
            }
        });

        const updateTextPositions = () => {
            curveTextMap.forEach((text, curve) => {
                const boundingBox = curve.getClientRect();
                const curveCenterX = boundingBox.x + boundingBox.width / 2;
                const curveCenterY = boundingBox.y + boundingBox.height / 2;
                text.position({ x: curveCenterX, y: curveCenterY });
            });
            this.layer.batchDraw();
        };

        this.layer.on('dragmove', updateTextPositions);

        const handleReadGainButtonClick = () => {
            if (selectedCurve) {
                const text = curveTextMap.get(selectedCurve);
                if (text) {
                    text.text(`${document.getElementById('quantity').value}`);
                    let curveKey;
                    this.curveLineMap.forEach((value, key) => {
                        if (value._id === selectedCurve._id) {
                            curveKey = key;
                            return;
                        }
                    });
                    if (curveKey) {
                        this.gains[`${curveKey}`] = document.getElementById('quantity').value;
                    } else {
                        console.error('Start or end ID of the curve is undefined.');
                    }
                    document.getElementById('quantity').value = '';
                    selectedCurve.stroke(selectedCurve.originalColor);
                    selectedCurve = null;
                }
            } else {
                console.log('Please select a curve arrow first.');
            }
        };

        document.getElementById('readGainButton').addEventListener('click', handleReadGainButtonClick);
    },

    read_gain() {
            const gainValue = parseFloat(document.getElementById('quantity').value);
            return gainValue ;
    },
    async createGraph(){
        let parts = []

        for( let i=0; i<this.node_id-1; i++ ){
            this.graph[i] = [];
        }

        for (let [key, value] of Object.entries(this.gains)) {
            parts = key.split("_");
            
//            parts[0] = String(parseInt(parts[0]) - 1)
//            parts[1] = String(parseInt(parts[1]) - 1)

            if(value.length === 0)
                value = 1
            console.log(parts)
            if (!this.graph[parts[0]]) {
                this.graph[parts[0]] = [];
            }
            this.graph[parts[0]].push([parts[1], value]);
        }

        for( let i=0; i<this.node_id; i++ ){
            if (!this.graph[i]) {
                this.graph[i] = [];
            }
        }
    },
    async calculate(){

        var div = document.getElementById("hiddenDiv");
        div.style.display = "block";
/*        this.graph = [[[1, 3]], // Numbers for index 0
            [[2, 4], [3, 5], [6, 3]],    // Numbers for index 1
            [[1, 4], [3, 2]],    // Numbers for index 1
            [[2, 4], [4, 2]],    // Numbers for index 1
            // Add more arrays for additional indices as needed
            [[3, 45], [5, 2]], // Numbers for index 2
            [[4, 45], [6, 2]], // Numbers for index 2
            [[6, 45], [7, 2], [5, 2], [4, 2]], // Numbers for index 2
            [],
            // Numbers for index 2
    ]
  */      


        // this.graph = [
        //         [["1", "1"]],
        //         [["3", "6"]],
        //         [["1", "-2"]],
        //         [["2", "-2"], ["4", "6"]],
        //         [["6", "6"]],
        //         [["4", "-2"]],
        //         [["5", "-2"], ["7", "1"]],
        //         []] 
                

//         this.graph = [
//   [
//     [
//       "1",
//       "1"
//     ]
//   ],
//   [
//     [
//       "1",
//       "-2"
//     ],
//     [
//       "2",
//       "4"
//     ]
//   ],
//   [
//     [
//       "3",
//       "4"
//     ]
//   ],
//   [
//     [
//       "4",
//       "4"
//     ]
//   ],
//   [
//     [
//       "2",
//       "-2"
//     ],
//     [
//       "5",
//       "1"
//     ]
//   ],
//   []
// ]
       await this.createGraph(this.graph)
        console.log(this.graph)
        

        await fetch("http://localhost:8080/receiveGraph",{
        method: "post",
        headers: {
          'Content-type': "application/json; charset=UTF-8"
        },
        body: JSON.stringify(this.graph),
      })

        let res = await fetch("http://localhost:8080/paths")
        this.paths = await res.json()

        res = await fetch("http://localhost:8080/allIndividualsLoops")
        this.loops = await res.json()

        res = await fetch("http://localhost:8080/allDeltasOfAllPaths")
        this.triangles = await res.json()

        res = await fetch("http://localhost:8080/delta")
        let delta = await res.json()
        this.triangles.splice(0, 0, delta);

        let array, string;
        for( let i=0; i<=this.loops.length/2; i++ ){
            res = await fetch(`http://localhost:8080/allKthNonTouchingloops?k=${i+2}`)
            this.nonLoops[i] = ""
            array = await res.json()
            console.log(array[0])
            for( let j=0; j<array.length; j++ ){
                this.nonLoops[i] += array.join(",") + "   "
            }
            // this.nonLoops[i] += ""

        }
        console.log(this.nonLoops)

        res = await fetch('http://localhost:8080/transferFunction')
        this.transferFn = await res.json()

    },
    hideDiv() {
        var div = document.getElementById("hiddenDiv");
        div.style.display = "none"; // Hide the div when button is clicked
    },
    nonTouchingLoops(nonLoopsList) {
        if( !nonLoopsList )
                return "No Non Touching Loops"

        return nonLoopsList.join(", ");
    }

},
computed: {

}

}
</script>
@import url('https://fonts.googleapis.com/css2?family=Grand+Hotel&display=swap');

<style scoped>
  #container{
    top           : 10%       ;
    left          : 5px       ;
    position      : fixed     ;
    width         : 99.5%     ;
    height        : 89.5%     ;
    border        : 4px solid ;
    border-radius : 20px 20px 20px 20px ;
    box-shadow    : 0 0 10px rgba(0, 0, 0, 1);  
  }
  .items{
    top      : 20px  ; 
    left     : 5px   ;
    position : fixed ;
  } 
  .btn{
    box-shadow : 0 0 15px rgba(0, 0, 0, 0.5);
    margin     : 5px;
  }

  label{
    margin-left  : 850px ;
    margin-right : 10px ;
    font-family  : 'Grand Hotel', cursive;
  }

  #quantity{
    box-shadow: 0 0 7px rgba(0, 0, 0, 0.5);
    width: 300px;
    border-radius: 15px 15px 15px 15px;
    padding: 5px;
    margin-left: 5px;
    margin-right: 20px;
  }

  #hiddenDiv {
  display: none; /* Hide the div by default */
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent black background */
}

#hideCalc {
    position: absolute;
    right: 5%;
    top: 5%;
    size: 10%;
}

#allInfo {
    position: absolute;
    top: 50%;
    left: 50%;
    background: white;
    height: 80%;
    width: 50%;
    transform: translate(-50%, -50%);
    border: 2px solid; /* Define the border as solid */
    outline: 2px dashed; /* Define the outline as dashed */
    padding: 5%;
    border-radius: 5%;
    font-size: 200%;
    overflow: scroll;
}
#toLeftPlease {
    text-align: left;
}
/* Define scrollbar track */
::-webkit-scrollbar {
  width: 10px; /* Width of the scrollbar */
}

/* Define scrollbar handle */
::-webkit-scrollbar-thumb {
  background: #888; /* Color of the scrollbar handle */
  border-radius: 5px; /* Rounded corners */
}

/* Define scrollbar track on hover */
::-webkit-scrollbar-track:hover {
  background: #f0f0f0; /* Background color on hover */
}

/* Define scrollbar handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555; /* Color of the scrollbar handle on hover */
}

</style>
