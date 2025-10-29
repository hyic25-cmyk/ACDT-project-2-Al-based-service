# ACDT-project-2-Al-based-service
<!doctype html>
<html lang="ko">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>활동 기록 (팀용)</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <div style="display:flex;align-items:center;justify-content:space-between;gap:12px;">
      <div>
        <h1>우리 활동 기록</h1>
        <p class="subtitle">팀 공유용 타임라인 — 공개 보기, Google 로그인으로 편집</p>
      </div>
      <div id="auth-area" style="text-align:right">
        <div id="user-info" style="display:inline-block;vertical-align:middle"></div>
        <button id="sign-in" style="margin-left:8px">Google로 로그인</button>
        <button id="sign-out" style="display:none;margin-left:8px">로그아웃</button>
      </div>
    </div>
  </header>

  <main>
    <section class="form-section">
      <h2>새 활동 추가</h2>
      <form id="activity-form">
        <div class="row">
          <label for="date">날짜</label>
          <input type="date" id="date" required />
        </div>
        <div class="row">
          <label for="title">제목</label>
          <input type="text" id="title" placeholder="예: 워크숍 참여" required />
        </div>
        <div class="row">
          <label for="description">설명</label>
          <textarea id="description" rows="4" placeholder="활동에 대한 상세 설명"></textarea>
        </div>
        <div class="row">
          <label for="tags">태그 (쉼표로 구분)</label>
          <input type="text" id="tags" placeholder="예: 회의,프로젝트" />
        </div>
        <div class="row">
          <label for="link">관련 링크 (선택)</label>
          <input type="url" id="link" placeholder="https://..." />
        </div>
        <div class="form-actions">
          <button type="submit" id="add-btn">추가</button>
          <button type="button" id="clear-btn">입력 초기화</button>
        </div>
      </form>
    </section>

    <section class="controls">
      <input type="text" id="search" placeholder="검색: 제목/설명/태그" />
      <select id="filter-tag">
        <option value="">모든 태그</option>
      </select>
      <div class="export-import">
        <button id="export-json">내보내기 (JSON)</button>
        <label class="file-label">
          <input type="file" id="import-json" accept="application/json" />
          가져오기 (JSON)
        </label>
        <button id="clear-all" class="danger">모두 삭제</button>
      </div>
    </section>

    <section class="timeline" id="timeline">
      <!-- 활동 항목이 여기 렌더링 됩니다 -->
    </section>
  </main>

  <footer>
    <small>저장: Firestore(권장) 또는 localStorage(폴백). 공개 보기(로그인 없이 조회 가능).</small>
  </footer>

  <!-- Firebase SDK (compat) - 자리표시 사용 -->
  <script src="https://www.gstatic.com/firebasejs/9.22.2/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/9.22.2/firebase-auth-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/9.22.2/firebase-firestore-compat.js"></script>

  <script src="script.js"></script>
</body>
</html>
