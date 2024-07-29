## 문제 상황

1. API 문서가 여러 군데에서 관리되어 '최신 API 문서'가 어디에 존재하는지에 대한 인지부하가 존재합니다.
2. API 문서 수정 시, 반영된 사항이 코드에 곧바로 반영되지 않거나, FE/BE 모두 한 곳을 바라보지 않을 수 있습니다.
3. 휴먼 에러로 인한 API 설계의 문제가 발생할 수 있습니다.

## 해결 방안

- FE, BE 모두 함께 API 문서를 설계합니다. 이때, 관리는 `.yaml` 형식의 [OpenApi 3.1 specification](https://swagger.io/specification/)을 따릅니다.
- 해당 문서를 기반으로, 백엔드 코드 제너레이터를 활용해 Swagger interface를 생성합니다. 이때, 수정이 일어나는 경우 해당 interface를 수정하는 것이 아닌, 전체 yaml 파일을 수정한 뒤
  이를 적용하도록 합니다.
- (가능하다면) 제공하는 Swagger interface에 대한 Mock server를 구현해 최대한 빠르게 FE 측에 제공합니다.
- API 설계 - 코드 반영 - 피드백을 빠르게 순환하도록 하며, 이를 통해 개발 효율성을 높일 수 있습니다.

## 무엇이 다른가요?

- 기존에는 코드 먼저 구현한 뒤, 이를 기반으로 하는 API 문서화를 진행했습니다.
- 해당 방법을 활용한다면 API 문서화를 먼저 진행한 뒤, 코드가 뒤따르는 형태가 됩니다.
- API 문서 또한 버저닝이 가능합니다. `yml` 파일을 우선적으로 수정하고 이를 코드에 반영하는 형태이기 때문에, Git과 같은 VCS에서 변경 이력을 확인하는 것이 매우 용이합니다.


## 어떻게요?

(공부 중이라, 차근차근 추가해 보겠습니다 )

## 참고한 것
- 인프콘 2023: 오늘도 여러분의 API는 안녕하신가요?: API First Design과 CodeGen 활용하기 (무료 강의로 열려 있습니다!)
- https://github.com/LenKIM/openapi-code-gen (위 발표의 참고 Github Repository)
- https://openapi-generator.tech/ (Codegen)
