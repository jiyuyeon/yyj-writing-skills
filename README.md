# yyj-writing-skills

문서 작성용 Claude Code 스킬 모음. 한국어 가공 산출 문서(PRD·리서치·회의록 등)의 작성 규칙을 슬래시 명령으로 자동 점검한다.

## 수록 스킬

| 스킬 | 호출 | 하는 일 |
|---|---|---|
| `yyj-doccheck` | `/yyj-doccheck [파일경로] [--fix]` | 막연한 형용사·출처 없는 수치·단정어·확증편향·줄글 단락·에세이형 제목·용어집 섹션·풀어쓰지 않은 약어를 grep으로 점검하고 수정안을 제시 |

## 설치

Claude Code는 `~/.claude/skills/` 안의 스킬을 자동 인식한다. 이 repo를 clone한 뒤 각 스킬을 그쪽으로 심볼릭 링크하면 끝.

```bash
# 1. 원하는 위치에 clone
git clone https://github.com/jiyuyeon/yyj-writing-skills.git ~/yyj-writing-skills

# 2. 스킬을 ~/.claude/skills 로 링크
ln -s ~/yyj-writing-skills/skills/yyj-doccheck ~/.claude/skills/yyj-doccheck

# 3. Claude Code 재시작 → /yyj-doccheck 사용 가능
```

심볼릭 링크가 번거로우면 폴더째 복사해도 된다.

```bash
cp -R ~/yyj-writing-skills/skills/yyj-doccheck ~/.claude/skills/yyj-doccheck
```

링크 방식은 `git pull`로 받은 업데이트가 즉시 반영되고, 복사 방식은 받을 때마다 다시 복사해야 한다.

## 업데이트

```bash
cd ~/yyj-writing-skills && git pull
```

링크로 설치했다면 그걸로 끝. 복사로 설치했다면 위 `cp` 명령을 다시 실행한다.

## 새 스킬 추가

`skills/<스킬이름>/SKILL.md` 형식으로 폴더를 추가한다. 폴더명과 `SKILL.md`의 `name:` 필드가 일치해야 한다.

```
skills/
  yyj-doccheck/
    SKILL.md
  yyj-<다음스킬>/
    SKILL.md
```
