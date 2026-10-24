# 구구 주임 — 게임용 캐릭터

- `gugu-manager.glb`: 텍스처가 필요 없는 glTF 2.0 바이너리. 모델, 색상 재질, `Idle`(2초) / `Flight`(1초) 루프 애니메이션 포함.
- `gugu-manager.blend`: Blender 4.3 편집 파일. GLB에서 가져온 모델·애니메이션과 별도 Studio 컬렉션의 카메라·조명이 들어 있습니다.
- `gugu-manager.json`: 삼각형 수, 파일 크기와 구성 정보.

30,780개 삼각형, 45개 렌더 메시, GLB 약 3MB. 별도 이미지·외부 리소스 없이 사용할 수 있습니다. 모델 뷰어에서 드래그로 회전하고 대기·비행, 앞·옆·뒤 시점을 확인할 수 있습니다.

모델은 +Y가 위, +Z가 정면입니다. Blender는 가져올 때 Z-up으로 변환합니다. `head`, `wing_L`, `wing_R`, `foot_L`, `foot_R`, `tie`, `badge`, `briefcase`, `tail` 등의 이름을 가진 오브젝트 관절로 구성했습니다. 스킨/웨이트가 있는 전신 스켈레톤 대신 각 부위를 회전시키는 방식입니다. 애니메이션을 GLB에서 재생하거나 개별 관절을 조작할 수 있습니다. Blender에서는 Object 모드와 NLA 트랙으로 편집하세요.

게임과 다운로드 모델은 동일한 `game/pigeon.ts` 정의에서 만들어집니다. 새로 생성하려면 저장소에서 `npm run model:export`를 실행하세요. Blender 편집 파일은 `blender -b --python scripts/pigeon-blend.py`로 다시 만들 수 있습니다. `.blend`의 Studio 컬렉션은 게임 GLB에 들어 있지 않습니다.
