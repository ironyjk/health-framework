# Health & Training Framework

건강·트레이닝 의사결정을 위한 메타 라우터 + 프레임워크 컬렉션.

영양(지중해식·저탄수·간헐적 단식·매크로 트래킹), 훈련(점진적 과부하·근력·근비대·지구력), 수면·회복, 측정·진단(혈액 바이오마커·체성분) 12개 프레임워크를 하나의 라우팅 레이어에 묶는다.

## 설계 원칙

1. **근거 기반(evidence-based)만** — RCT·메타분석·코크란 리뷰가 뒷받침하는 것만. 유사과학·인플루언서 마케팅·식이보조제 업계 주장은 배제.
2. **증거 강도를 명시** — "강한 증거"(예: PREDIMED·점진적 과부하) / "보통"(예: 16:8 TRE) / "약함 또는 논쟁 중"(예: 대부분 보조제)을 구분.
3. **목적·개인 맥락 우선** — "감량 vs 증량 vs 지구력 vs 건강수명" 목적에 따라 같은 프레임워크가 달라진다.
4. **과적용 경고 포함** — 각 프레임워크가 역효과를 내거나 지속 불가능할 때를 명시.

## 구조

```
health-framework/
├── SKILL.md                   # 메타 라우터 — 상황 → 프레임워크 선택
├── mediterranean-diet/        # PREDIMED 기반, 가장 강한 장기 증거
├── low-carb-keto/             # 케토제닉 · 대사적응 · 적용 대상
├── intermittent-fasting/      # 16:8 · 5:2 · TRE
├── macro-tracking/            # 칼로리 + 단백질 · 탄/지 목적별 배분
├── progressive-overload/      # 모든 훈련의 근본 원칙
├── strength-basics/           # 5x5 · 5/3/1 · Starting Strength
├── hypertrophy-volume/        # MV/MEV/MAV/MRV · PPL · RP
├── polarized-endurance/       # Seiler 80/20 · Z2 + VO2max
├── sleep-foundations/         # 7~9h · 일관성 · 광노출
├── recovery-periodization/    # SRA · HRV · deload
├── blood-biomarkers/          # ApoB · HbA1c · hs-CRP · 비타민D
└── body-composition/          # DEXA · BIA · FFMI · 허리둘레
```

## 사용

```
/health-framework <상황 설명>
```

메타 라우터가 목적·증상·레벨을 분류해 1~3개 프레임워크를 선택, Skill 툴로 실행·합성.

## 범위 바깥

- 질병 치료·약물 처방 (→ 의사)
- 정신건강·심리 상담 (→ `counsel`)
- 스포츠 종목별 기술 코칭 (→ 해당 종목 전문가)
- 임산부·소아·고령 특수 상황 (→ 전문의)

## 면책

**이 레포는 의사결정 보조 도구이며 의료·영양 자문이 아니다.**

- 기저질환(당뇨·심혈관·신장·갑상선·자가면역 등)이 있거나 약물 복용 중이면 변경 전 반드시 의사·영양사와 상담할 것.
- 제시되는 수치(단백질 g/kg, 목표 심박수, 바이오마커 참고범위 등)는 일반 성인 기준이며, 개인 편차가 크다.
- 보조제·식이·훈련 프로토콜 변경으로 인한 결과에 대한 책임은 본인에게 있다.
- 급성 증상(흉통·실신·심한 피로·체중 급변 등)은 프레임워크가 아니라 병원 진료가 우선이다.
