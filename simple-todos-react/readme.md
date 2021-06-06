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

## 비밀번호 인증

> Meteor에는 이미 기본 인증 및 계정 관리 시스템이 기본 제공되므로  <br/> 사용자 이름 및 비밀번호 인증을 활성화 하려면 accounts-password을 추가하기 만하면됩니다.<br/>
> 설치 : meteor add accounts-password , meteor npm install --save bcrypt 

## 클라이언트 측 데이터베이스 권한을 취소 

> 설치 : meteor remove insecure <br/>
  -> 클라이언트 측에서 데이터베이스에 접근 권한을 차단한다.