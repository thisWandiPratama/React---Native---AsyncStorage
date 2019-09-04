# React Native AsyncStorage 
AsyncStorage is a simple, unencrypted, asynchronous, persistent, key-value storage system that is global to the app. It should be used instead of LocalStorage.

### `` Menyimpan Data di Perangkat User``

```
AsyncStorage adalah sistem penyimpanan nilai kunci yang simpel, tidak terenkripsi, asinkron, persisten, dan bersifat global bagi aplikasi. Ini harus digunakan sebagai pengganti LocalStorage.
```
Untuk mengilustrasikan penggunaan AsyncStorage kita akan membuat sebuah aplikasi sederhana yang meminta user untuk menginput nama dan hobinya. Data yang diinputkan oleh user akan ditampilkan di layar dan disimpan di perangkat sehingga ketika aplikasi di-kill dan dibuka kembali, aplikasi dapat menampilkan kembali data yang sebelumnya sudah dimasukkan.

## Create Project
```
react-native init RNAsyncStorage --version react-native@0.59.5
$ cd RNAsyncStorage
```

#### ``App.js``

```
import React, { Component } from 'react';
import { AppRegistry, AsyncStorage, Button, StyleSheet, Text, TextInput, View } from 'react-native';

class RNAsyncStorage extends Component {
    constructor() {
        super();
        this.state = {
            name: '',
            hobby: '',
            textName: '',
            textHobby: ''
        };
    }

    render() {
        return (
            <View style={styles.container}>
                <Text style={styles.welcome}>
                    Halo! Kenalan yuk!
                </Text>
                <Text style={styles.instructions}>
                    Nama: {this.state.name}{'\n'}
                    Hobi: {this.state.hobby}
                </Text>
                <TextInput style={styles.textInput}
                    onChangeText={(textName) => this.setState({textName})}
                    placeholder='Nama'
                />
                <TextInput style={styles.textInput}
                    onChangeText={(textHobby) => this.setState({textHobby})}
                    placeholder='Hobi'
                />
                <Button
                    title='Simpan'
                    onPress={() => {}}
                />
            </View>
        );
    }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'flex-start',
    alignItems: 'center',
    backgroundColor: '#F5FCFF',
    padding: 16,
    paddingTop: 32
  },
  welcome: {
    fontSize: 20,
    textAlign: 'center',
    margin: 10,
  },
  instructions: {
    textAlign: 'center',
    color: '#333333',
    marginBottom: 5,
  },
  textInput: {
    height: 35,
    backgroundColor: 'white',
    marginTop: 8,
    marginBottom: 8,
    borderWidth: 1,
    borderColor: 'grey',
    padding: 8
  }
});


export default RNAsyncStorage;

```
