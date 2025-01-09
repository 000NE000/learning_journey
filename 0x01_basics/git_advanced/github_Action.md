## 구성요소

> Github Action을 이해하기 위해서 알아야 하는 개념은 Workflow, Event, Job, Step, Action, Runner 등이 있음
#### Workflow
- 여러 Job으로 구성되고, Event에 의해 트리거될 수 있는 자동화된 프로세스
- 최상위 개념
- Workflow 파일은 YAML으로 작성되고, Github Repository의 .github/workflows 폴더 아래에 저장됨

#### Event
- Workflow를 Trigger(실행)하는 특정 활동이나 규칙
    - 예를 들어 다음과 같은 상황을 사용할 수 있음
        - 특정 브랜치로 Push하거나
        - 특정 브랜치로 Pull Request하거나
        - 특정 시간대에 반복(Cron)
        - Webhook을 사용해 외부 이벤트를 통해 실행
        
#### Job
- Job은 여러 Step으로 구성되고, 가상 환경의 인스턴스에서 실행됨    
- 다른 Job에 의존 관계를 가질 수 있고, 독립적으로 병렬 실행도 가능함
#### Step
- Task들의 집합으로, 커맨드를 날리거나 action을 실행할 수 있음
#### Action
- Workflow의 가장 작은 블럭(smallest portable building block)
- Job을 만들기 위해 Step들을 연결할 수 있음
- 재사용이 가능한 컴포넌트

#### Runner
- Gitbub Action Runner 어플리케이션이 설치된 머신으로, Workflow가 실행될 인스턴스
- Github에서 호스팅해주는 Github-hosted runner와 직접 호스팅하는 Self-hosted runner로 나뉨
    