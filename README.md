# React SmartTV Dimention


Library ensures proper height, width, font ratio SmartTV Tizen, WebOS: 1920x1080



## Installation

Using npm:

```
npm install --save @react4tv/react-tv-dimention
```

or using yarn:

```
yarn add @react4tv/react-tv-dimention
```

## Usage

Full Examples:

```javascript
import { 
    DimentionProvider, 
    withDimentionContext,
    ScaleUtil
} from '@react4tv/react-tv-dimention';

class AppContainer extends React.Component {
  constructor(props) {
    super(props);
  }

  componentDidMount() {
    window.addEventListener('resize', this.resizeDocument);
  }

  componentWillUnmount() {
    window.removeEventListener('resize', this.resizeDocument);
  }

  private resizeDocument = () => {
    ScaleUtil.changeScaleRatio();
    this.props.dimentionContext.setAppDimention();
  };

  render(){
    const { width, height } = this.props.dimentionContext.dimention;
    return (
      <DimentionProvider>
        //...
      </DimentionProvider>
    );
  }
}

const App = withDimentionContext(AppContainer);

//Container
ReactDOM.render(<App />, "root");

```

## Example

![alt text](https://github.com/react-4-smart-tv/react-tv-dimention/blob/main/img/1.png?raw=true)


![alt text](https://github.com/react-4-smart-tv/react-tv-dimention/blob/main/img/2.png?raw=true)

