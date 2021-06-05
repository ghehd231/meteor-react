# meteor 정리
 
## useTracker
> react-meteor-data는 React 컴포넌트에서 반응성을 가질 수있게 해주는 React Hook <br/> 데이터가 변경 될 때마다 구성 요소가 다시 렌더링<br/>
> 설치 : meteor add react-meteor-data

``` import React from 'react';
import { useTracker } from 'meteor/react-meteor-data';
import { TasksCollection } from '/imports/api/TasksCollection';
import { Task } from './Task';
 
export const App = () => {
  const tasks = useTracker(() => TasksCollection.find({}).fetch());
 
  return (
    <div>
      <h1>Welcome to Meteor!</h1>
 
      <ul>
        { tasks.map(task => <Task key={ task._id } task={ task }/>) }
      </ul>
    </div>
  );
}; 
```
test