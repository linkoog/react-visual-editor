# @brickd/core

> TODO: description

###  📦 Install
```sh
yarn add @brickd/react  @brickd/react-web @brickd/render
```
OR
```sh
npm install @brickd/react @brickd/react-web @brickd/render
```
## Usage
```jsx
import {createElement} from 'react';
import {BrickDesign,BrickTree,BrickProvider,useSelector,createActions} from '@brickd/react';
import {BrickPreview} from '@brickd/react-web';
import BrickRender from '@brickd/render';
const plugins=[(vDom,componentConfig)=>vDom];
const customReducer=(state,action)=>{
const {type,payload}=action
switch (type){
case 'customReducer':
return {...state}
default:
return state
}

}
const App = () => {
const {componentConfigs}=useSelector(['componentConfigs'])

	return(<BrickProvider initState={{}} customReducer={customReducer} config={{...}}>
<div onClick={()=>createActions({type:"customReducer",payload:{...}})}> 出发action</div>

    <BrickPreview/>
    <BrickDesign />
<BrickRender componentConfigs={componentConfigs} createElement={createElement} plugins={plugins}/>
<BrickTree/>

  </BrickProvider>);
}
```
