# Release Drafter

[Release Drafter](https://github.com/release-drafter/release-drafter) 는 Release 정보 관리를 자동화하는데 도움이 되는 도구이자 Github Action 입니다. 이 도구는 Pull Request Metadata ( Commit header, link ) 등을 이용하여 ChangeLog 초안을 생성한 다음 Draft 된 새 버전의 Release 를 만들어줍니다. 

## Usage

`.github` 레포에 글로벌 공통 파일이 존재하고, 사용할 레포에서 해당 설정을 가져오는 식으로 사용합니다.

### Release Drafter 활성화하기

사용중인 설정으로 확인 가능합니다.

- .github/release-drafter.yml
- .github/workflow/release-drafter.yml

### Releease Drafter 설정하기

레포에서 활성화 한 후 `.github/release-drafter.yml` 을 기본 브랜치에 생성합니다.

메이사에서는 공통 구성 파일을 제공해주므로, 최소 설정은 다음과 같습니다.

```yml
# Release drafter configuration https://github.com/release-drafter/release-drafter#configuration
# Emojis were chosen to match the https://gitmoji.carloscuesta.me/
_extends: .github
```

모든 글로벌 설정은 레포에서 재정의할 수 있습니다. 필요한 경우 처음부터 작성할수도 있습니다.


#### 글로벌 설정에서 고려해야 할 사항

- 기본적으로 `v${MAJOR}.{MINOR}.{PATCH}` 형태의 릴리즈 방식을 따릅니다.
