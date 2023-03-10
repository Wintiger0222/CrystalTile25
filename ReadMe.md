# CrystalTile2.5
크리스탈타일2 개선판

소스코드를 구할수 있는 가장 최근 버전인 크리스탈 타일2 2007.09.12 판에서 SNES 4bpp 문제점을 해결한 버전입니다.
# 구현된 사항
 * SNES 4bpp 모드에서 GB 2bpp 로 출력하는 문제점 해결
 * 테스트용 3bpp 모드 추가
 
# TODO(Canceled)
프로젝트의 너무 낡음과 CrystalTree의 불안정성, 진행자의 윈도우 프로그래밍에 대한 이해도 때문에 진행을 취소합니다.
만약에 MFC등 윈도우 프로그래밍에 익숙한 사람이 참여할 경우 다시 진행될 가능성이 있습니다.
 * 64비트 이식 (MFC 오류 해결 필요)
 * 그래픽 모드 추가
  ```
  - 크리스탈타일2 2011버전에서 지원하는 모드
  16색 BGRa
  32색 aBGR
  3BPP 3색
  Tim 8bit 규격
  
  - YY-CHR에서 지원하는 모드
  2BPP MSX (2BPP NES의 변종)
  2BPP MSX Screen 2 (16색 모드)
  3BPP 8x8 (2bpp NES의 확장)
  3BPP SNES (2bpp NES + 1bpp 단색)
  4BPP PCE(SG) (16x16)
  4BPP MSX/MD/WSC (4BPP GBA의 변종)
  4BPP 8x8 (2bpp NES의 확장)
  8BPP SNES(128x128) (4bpp SNES의 확장)
  
  - 기타
  4BPP MD/x68k (2BPP VB/NGP의 4BPP 확장, 위의 4BPP MSX/MD/WSC와 동일한지 확인 필요, https://mrclick.zophar.net/TilEd/download/consolegfx.txt)
   ```
 * 이외 기존 크리스탈 타일의 업데이트 내역
```
2009.03.06 구현사항
1. 압축 및 압축 해제 기능이 콘솔에 추가됩니다.
2. PAC 파일 열기 오류 로그아웃 오류를 수정한다.
3.NFTR 라이브러리 에디터 코드 테이블 내보내기 기능 추가(글꼴 순으로 저장)

4. OCR 문자 인식 기능 추가
　9, 11, 15 크기 인식 가능
　템플릿을 선택할 때 가능한 한 작은 템플릿을 사용하십시오
　예를 들어 어떤 게임의 글자모양은 16자모이고 사실 글자는 보통 12, 14, 15입니다.
　어떤 12개의 글자 모양은 사실 문자는 모두 9, 10, 11 등등이다.
　그래서 9, 11, 15는 사실 게임에서 일반적으로 사용되는 글자 모양 크기를 이미 포함하고 있습니다.

　인식시 프로그램은 검정색을 바탕색으로 사용하므로 문자 팔레트의 바탕색은 검정(RGB(0,0,0)을 사용하십시오.
　테스트 진행 시 1BPP 단색에 대한 라이브러리 인식률이 매우 좋습니다.
　다중 색상 라이브러리의 경우 주 색상 스와치를 한 가지 색상으로 설정하고 다른 색상을 검은색으로 설정하는 것을 고려할 수 있습니다.
　이렇게 하면 단색의 목적을 달성할 수 있습니다.

2009.02.2 구현사항
1. Header=0x11의 LZ압축, 해제 지원
2. 안티에이징 카드 코드 제거 기능 추가
3.NEF 심볼 라이브러리 확장
4. NFTR 라이브러리 편집기 다시 쓰기
　NFTR의 모든 기능 지원
　NFTR 기본 라이브러리 지원
　Korean (CodePage 949 / UHC)
　European Language (CodePage 1252 / Latin-1)
　DS-IPL font table
　DS-IPL font table for Chinese
　DS-IPL font table for Korean
　Japanese Level 1 (JIS X 0208)
　Japanese Level 1,2 (JIS X 0208)

2009.02.05 구현사항
1. NANR/NCER/NCGR/NCLR 애니메이션 지원
　NANR/NCER/NCBR/NCLR 动画
　NCLR 팔레트가 없는 경우 CT2 자체 팔레트 사용

2. NCLR 확장 팔레트 지원 (256색 팔레트 16개 내장)
　팔레트 창에는 0123456789ABCDEF 번호가 매겨진 16개의 팔레트가 있습니다

2009.01.22 구현사항
1.NO$GBA 2.6A 일반 및 디버거 버전, iDeas 1.0.2.7 팔레트 로딩 기능 추가(에뮬레이터 먼저 실행)
2. 16진수 편집기의 문자열 처리 향상
　데이터에서 커서: 데이터 복사
　커서 위치 문자: 문자 복사
3. 더 많은 문자 집합 지원
4.HUFFMAN 데이터 압축, 압축 해제 지원
　LZ77 압축에서 VRAM 지원 포맷으로 변경 (이전에는 16비트를 지원하지 않음)

5.비트맵 부착 기능 강화
　Tile 대 Tile로 붙여넣을 수 있습니다.
　두 비트맵에 대한 Tile 크기가 다른 경우
　단축키:Alt+Shift+상하좌우(컷팅정보가 상태바에 표시됨)
　두 줄 두 줄의 16x16Tile을 복사하여 12x12Tile에 붙여넣기
　줌 기능을 사용하여 두 개의 Tile 콘텐츠를 하나의 Tile에 넣을 수도 있습니다.
　이전에는 Tile에 대해 Tile을 붙여넣을 수 없었습니다.

7.NEF 기호표 생성 도구 추가
　추적을 더 쉽게 하기 위해 NO$GBA 디버거에 사용할 수 있습니다.
　NitroSDK3, 4, MONGOOSE3, 4(ARM7 Components)의 대부분의 함수를 포함합니다.
　여러 심볼 라이브러리 검색을 선택하는 것은 권장되지 않으며 CT2에서 게임 개발 라이브러리 버전을 확인합니다.
　기호 규칙
　분류[i]_기호명
　예를 들어 FS_ReadFileMIi_CpuClear32i는 개인 함수를 나타냅니다
　CT2에 추가된 기호 규칙:
　만약 당신이 ARM9과 ARM7의 기호표를 동시에 만든다면
　CT2는 NO$GBA가 동일한 이름의 기호를 처리할 수 없기 때문에 ARM7 기호 뒤에 '7'을 자동으로 추가합니다.
　예: OS_Init, NO$GBA는 첫 번째 ARM9의 OS_Init만 점프할 수 있으며, ARM7의 OS_Init은 점프할 수 없습니다.
　하지만 정상적으로 표시되며 OS_Init7로 변경 후 NO$GBA에 심볼 입력이 편리합니다.
　ARM7 심볼 라이브러리를 별도로 생성하는 경우 '7'이 추가되지 않습니다.

2008.02.28 구현사항
1.뒤집기 등 Tile 특수효과 실패 오류 수정

2008.02.21 구현사항
1.DS 파일 삽입 지원
2. DS 파일 목록 수정 일본어 파일 이름 깨짐 모두 오류

2008.01.22 구현사항
1.XAP 파일 지원

2007.12.28 구현사항
1. 단일 문서 다중 파일 열기 기능 개선
2.DS 파일 목록에서 NFTR 라이브러리를 직접 열 수 있음
3. 사운드 파일 저장 실패 오류 수정
4.NFTR 에디터의 CMAP 목록 오류 수정

2007.12.22 구현사항
1.LZ 대량 압축 기능 추가
2.NFTR 라이브러리 생성 기능 추가
3. DS 파일을 가져올 때 파일이 원래 파일보다 크면
　나중에 사용할 수 있는 공간을 먼저 자동으로 검색합니다. 사용자가 수동으로 새 공간 주소를 입력할 필요가 없습니다.
　찾을 수 없으면 새 주소를 입력하라는 메시지가 나타납니다(기본값은 DS 헤더의 ROM 끝 주소입니다).
4. 인트로 기능 추가, 이미지 256색 비트맵

2007.12.11 구현사항
1.DS 파일 목록을 디렉터리 + 목록으로 변경
2.새로운 파일 패키지 형식 지원
3.DS 파일 목록에 멀티미디어 기능 추가
4.Tile 뒤집기 처리 오류 수정
5.새 빈 파일 추가
6.파일 메뉴 추가파일 기능 추가　
```
== 프로젝트 저작자 ==
2004-2007 Crystal (C)
2010년도 까지 해당 제작자가 프로젝트를 진행하였으나, 지금 가지고 있는건 2007년 사본 밖에 없습니다.
원본 사본은 해당링크에서 다운로드 가능합니다.[https://filetrip.net/nds-downloads/utilities/download-crystaltile2-source-code-september-2007-f31478.html]
