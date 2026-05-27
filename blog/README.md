# Blog

## 새 글 추가하기

### 1. Markdown 파일 작성

`posts/` 폴더에 `슬러그.md` 파일을 만든다.

- 파일명은 영문 소문자와 하이픈만 사용 (예: `my-new-post.md`)
- 내용은 일반 Markdown으로 작성

```markdown
# 포스트 제목

본문 내용...
```

### 2. manifest.json에 항목 추가

`posts/manifest.json`을 열어 배열에 항목을 추가한다.

```json
{
  "slug": "my-new-post",
  "title": "포스트 제목",
  "date": "YYYY-MM-DD",
  "description": "한 줄 요약 (선택사항)"
}
```

- `slug`: Markdown 파일명에서 `.md`를 뺀 것
- `description`은 목록 페이지에 표시되는 요약 문구 (없어도 됨)

### 3. 커밋 & 푸시

```bash
git add blog/posts/
git commit -m "Add new post: 제목"
git push
```

---

## 폰트 변경하기

`blog/config.json`에서 폰트를 설정한다.

```json
{
  "font": {
    "family": "Lora",
    "google_fonts_url": "https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,700;1,400;1,700&display=swap",
    "fallback": "Georgia, serif"
  }
}
```

- `family`: 사용할 폰트 이름
- `google_fonts_url`: Google Fonts에서 가져오는 경우 URL (없으면 시스템 폰트만 사용)
- `fallback`: 폰트를 불러오지 못할 때 대체 폰트

### 폰트 예시

| 폰트 | 분류 | Google Fonts URL |
|------|------|-----------------|
| Lora | Serif | `...family=Lora:ital,wght@0,400;0,700;1,400` |
| Merriweather | Serif | `...family=Merriweather:wght@300;400;700` |
| Playfair Display | Serif | `...family=Playfair+Display:wght@400;700` |
| Georgia | Serif (시스템) | URL 불필요, `family`를 `Georgia`로 설정 |
| Inter | Sans-serif | `...family=Inter:wght@400;700` |

> Google Fonts URL 전체 주소는 [fonts.google.com](https://fonts.google.com)에서 원하는 폰트를 선택 후 "Get embed code"에서 확인할 수 있다.

---

## URL 구조

| 페이지 | URL |
|--------|-----|
| 포스트 목록 | `/blog/` |
| 개별 포스트 | `/blog/post.html?slug=슬러그` |
