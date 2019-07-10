## react-native-read-more-text

[Try it on Expo](https://exp.host/@notbrent/read-more-text-example)

![Example](https://raw.githubusercontent.com/expo/react-native-read-more-text/master/example.gif)

### Installation

```
npm i https://github.com/Multiware-Tecnologia/react-native-read-more-text.git --save
```

### Usage

```javascript
import ReadMore from 'react-native-read-more-text'

export class DescriptionCard extends React.Component {
  render() {
    let { text } = this.props;

    return (
      <View>
        <View style={styles.cardLabel}>
          <BoldText style={styles.cardLabelText}>
            Description
          </BoldText>
        </View>

        <View style={styles.card}>
          <View style={styles.cardBody}>
            <ReadMore
              numberOfLines={3}
              renderTruncatedFooter={this._renderTruncatedFooter}
              renderRevealedFooter={this._renderRevealedFooter}
              onReady={this._handleTextReady}>
              <RegularText style={styles.cardText}>
                {text}
              </RegularText>
            </ReadMore>
          </View>
        </View>
      </View>
    );
  }

  _renderTruncatedFooter = (handlePress) => {
    return (
      <RegularText style={{color: Colors.tintColor, marginTop: 5}} onPress={handlePress}>
        Read more
      </RegularText>
    );
  }

  _renderRevealedFooter = (handlePress) => {
    return (
      <RegularText style={{color: Colors.tintColor, marginTop: 5}} onPress={handlePress}>
        Show less
      </RegularText>
    );
  }

  _handleTextReady = () => {
    // ...
  }
}
```
