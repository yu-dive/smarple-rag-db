# smarple-rag-db

스마트보고서 AI봇(크롬 확장)의 "법령 질의" 기능이 브라우저 안에서 검색할 때 쓰는 법령 조문 DB입니다.
GitHub Pages(`https://yu-dive.github.io/smarple-rag-db/`)로 게시되며, 확장이 `manifest.json`을 확인해 새 버전이 있으면 자동으로 받습니다.

- `manifest.json` — `db_version`(내용 해시), 생성일, 임베딩 모델·차원, 건수, 법령 정보(법령명·공포번호·시행일자), 파일별 sha256
- `chunks.json` — 조문 목록(위치, 법령명, 종류, 경로, 검수상태, 원문링크, 본문)
- `vectors.bin` — float32 little-endian 임베딩, 행 순서 = `chunks.json` 순서, 길이 1로 정규화

내용은 국가법령정보센터(law.go.kr)의 법령 원문이며 사람 검수를 마친 조문만 포함합니다.
법령은 저작권법 제7조에 따라 저작권 보호 대상이 아닙니다. 정확한 내용은 각 조문의 원문 링크로 확인하세요.

이 저장소의 파일은 직접 고치지 않습니다. 비공개 저장소 `smarple-rag`의 `extractor/export_db.py`로 생성합니다.
