# React_boolApp
when bool is true, showing the component 

Demo:

![bool](https://raw.githubusercontent.com/QueenieCplusplus/ReactNative_boolApp/master/demo_for_bool_is_true.png)


# Code

cat.js

      import * as React from 'react';
      import { Text, View, StyleSheet, Image, Button } from 'react-native';
      import TouchHistoryMath from 'react-native/Libraries/Interaction/TouchHistoryMath';

      export default class Poupou extends React.Component {


        constructor(props){
          super(props);
          this.state = {
            pressed: false,
            words: ""
          }
        }

        pressHandler = () => {
          this.setState({pressed: true, words: "Love!"})
        }

        render(){

          return (
            <View style={styles.container}>
              <Text style={styles.paragraph}>
                 My Poupou Cat
              </Text>

                {this.state.pressed  && <Text>{this.state.words}
              </Text>}
              <br/>
              <Image style={styles.logo} source={require('../assets/poupou.png')} />

              <br/>
              <Button color = "#841584" title= 'kiss poupou' size={10} onPress = {this.pressHandler}/>
            </View>
          );


        }

      }


      const styles = StyleSheet.create({
        container: {
          alignItems: 'center',
          justifyContent: 'center',
          padding: 24,
        },
        paragraph: {
          color: "#841584",
          margin: 24,
          marginTop: 0,
          fontSize: 22,
          fontWeight: 'bold',
          textAlign: 'center',
        },
        logo: {
          height: 128,
          width: 128,
        }
      });

App.js


            import * as React from 'react';
            import { Text, View, StyleSheet } from 'react-native';
            import Constants from 'expo-constants';

            // You can import from local files
            import Poupou from './components/cat';

            // or any pure javascript modules available in npm
            import { Card } from 'react-native-paper';

            export default function App() {
              return (
                <View style={styles.container}>
                  <Text style={styles.paragraph}>
                  </Text>
                  <Card>
                    <Poupou />
                  </Card>
                </View>
              );
            }

            const styles = StyleSheet.create({
              container: {
                flex: 1,
                justifyContent: 'center',
                paddingTop: Constants.statusBarHeight,
                backgroundColor: '#ecf0f1',
                padding: 8,
              },
              paragraph: {
                margin: 24,
                fontSize: 18,
                fontWeight: 'bold',
                textAlign: 'center',
              },
            });
