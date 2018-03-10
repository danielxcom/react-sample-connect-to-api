MOUNTING - happens when component is born in a DOM. 
constructor()
componentWillMount() - constructor done but before render() Before.
render() 
componentDidMount() - invoked after component markup in DOM. After.

UNMOUNTING - get off the horse!
Clean up something inside component!
Sort of a destructor!

componentWillUnmount - cleans up a setInterval after you loaded your program.


ETC....
https://reactjs.org/docs/react-component.html

##componentWillUnmount

    const NUM_BOXES = 32;
    
    class Boxes extends Component {
        constructor(props) {
            super(props);
            const boxes = Array(NUM_BOXES).fill()
                .map(this.getRandomColor, this);
            this.state = {boxes};
            
            this.intervalId = setInterval(() => {
                const boxes = this.state.boxes.slice();
                const ind = Math.floor(Math.random()*boxes.length);
                
                boxes[ind] = this.getRandomColor();
                this.setState({boxes});
            }, 300);
            }
            componentWillUnmount() {
                clearInterval(this.intervalId);
            }
        }
    }
    
ETC...