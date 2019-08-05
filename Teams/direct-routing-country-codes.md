---
title: 직접 라우팅 국가 코드
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 이 문서를 참조 하 여 직접 라우팅에 대 한 미디어 경로 국가 코드를 찾습니다.
ms.openlocfilehash: 8ab2a6b9dbcbb676362c9fc7e39637aff0724a53
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36184589"
---
# <a name="direct-routing-media-path-country-codes"></a>직접 라우팅 미디어 경로 국가 코드

미디어에 대 한 라우팅 경로를 선택할 때 직접 경로 지정은 기본적으로 SBC (세션 경계 컨트롤러)의 공용 IP 주소를 기반으로 데이터 센터를 할당 하 고 항상 SBC 데이터 센터에 가장 가까운 경로를 선택 합니다.

그러나 경우에 따라 기본 미디어 경로가 최적의 미디어 경로가 아닐 수 있습니다. 예를 들어 미국 범위의 공용 IP는 유럽에 위치한 SBC에 할당 될 수 있습니다. 

New-CsOnlinePSTNGateway 및 CsOnlinePSTNGateway cmdlet에-MediaRelayRoutingLocationOverride 매개 변수를 사용 하 여 미디어 트래픽에 대 한 기본 영역을 지정할 수 있습니다. 예를 들어 다음 명령을 실행 하면 기본 설정 영역이 독일로 지정 됩니다.

Set-CSOnlinePSTNGateway-Id sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

Microsoft는 미디어 경로에 대 한 데이터 센터의 기본 지정이 SBC 데이터 센터에 가장 가까운 경로를 사용 하지 않는다는 것을 호출 로그가 명확 하 게 표시 하는 경우에만이 매개 변수를 설정 하는 것이 좋습니다. 
 
## <a name="country-code-reference-table"></a>국가 코드 참조 표

다음 표에는-MediaRelayRoutingLocationOverride 매개 변수에 대 한 국가 코드 값이 나와 있습니다.

| 명칭         | 코드 
|-----------------|--------------------|
| 아프가니스탄     | AF |
| 알 랜드 제도   | AX |
| 알바니아         | AL.EXE |
| 알제리         | DZ |
| 미국령 사모아  | 문자열로 |
| (모든)         | 임시로 |
| 앙골라          | AO |
| Anguilla        | AL.EXE |
| 대륙      | AQ | 
| 앤티가 바부다 | AG |
| 아르헨티나       | AR |
| 아르메니아         | 중인 |
| 아루바           | AW |
| 오스트레일리아       | AU |
| 오스트리아         | 배포자 |
| 아제르바이잔      | 아리조나 |
| 바하마         | #A0 |
| 바레인         | BH |
| 방글라데시      | BD |
| 바베이도스        | BB |
| 벨로루시         | 여 |
| 벨기에         | 않을 |
| 벨리즈          | BZ |
| Benin           | 카트리지로 |
| 버뮤다         | (모두) |
| 부탄          | BT |
| 볼리비아         | 상자 |
| 보네르         | BQ |
| 보스니아 헤르체고비나 | 모음 |
| 보츠와나        | 용 |
| 부베이 섬   | BV |
| 브라질          | B |
| 영국 인디언 바다 영토 | 입출력 |
| 영국령 버진 아일랜드 | VG |
| 브루나이          | BN-BD&PLATFORM |
| 불가리아        | BG-BG&PLATFORM |
| 부르키나파소 부르키나파소    | BF |
| 부룬디         | 접 |
| 카보베르데      | 비용 |
| 캄보디아        | KH |
| 카메룬        | 5 |
| 캐나다          | 캐나다 |
| 케이맨 제도  | KY-KG&PLATFORM |
| 중앙 아프리카 공화국 | CF |
| Chad            | 요소나 |
| 칠레           | CL |
| 중국           | CN |
| 크리스마스 섬 | CX |
| 코코스 군도 | [ |
| 콜롬비아        | 보조 |
| 르         | KM |
| 공화국           | CG |
| 콩고 민주 공화국     | \ |
| 쿡 제도    | 머리 |
| 코스타리카      | 전송 |
| 코트디부아르   | CI |
| 크로아티아         | 못하여 |
| 쿠바            | CU ( |
| Curacao         | 회사 |
| 키프로스          | CY-GB&PLATFORM |
| Czechia         | CZ |
| 덴마크         | 진한 |
| 지부티        | DJ |
| 도미니카        | DM |
| 도미니카 공화국 | 필요가 |
| 에콰도르         | EC |
| 이집트           | 예: |
| 엘살바도르     | SV |
| 적도 기니 | GQ |
| 에리트레아         | 어 |
| 에스토니아         | EE |
| Eswatini        | SZ |
| 에티오피아        | ET |
| 포클랜드 제도 | 외래 |
| 페로 제도   | 라이브러리의 |
| 표준시            | FJ |
| 핀란드         | WI-FI |
| 프랑스          | US |
| 프랑스령 기아나   | GF |
| 프랑스령 폴리네시아 | 공용 |
| 프랑스 남쪽 지역 | HELP |
| Gabon           | GA |
| 감비아          | GM |
| 그루지야         | GE |
| 독일         | 로케이터 |
| 가 나           | GH |
| 지       | GI |
| 그리스          | GR |
| 표준시       | GL |
| Grenada         | GD-GB&PLATFORM |
| 과들루프      | P |
| 괌            | GU-IN&PLATFORM |
| 과테말라       | G |
| Guernsey        | GG |
| 기니          | GN |
| 기니-Bissau   | GW |
| 가이아나          | GY |
| 아이티           | 안녕 |
| 허드 섬 및 맥도널드 군도 | HM |
| 온두라스        | HN |
| 홍콩 특별 행정구   | HK |
| 헝가리         | HU-HU&PLATFORM |
| 아이슬란드         | 는 |
| 인도           | 에서는 |
| 인도네시아       | I |
| 이란            | IR |
| 이라크            | IQ |
| 아일랜드         | 지금은 |
| 남자 섬     | 메신저 |
| 이스라엘          | IL |
| 이탈리아           | 고 |
| 자메이카         | JM |
| 얀마웬       | XJ |
| 일본           | JA-JP |
| 뉴저지          | JE |
| 요르단          | 분 |
| 카자흐스탄      | KZ |
| 케냐           | 케 |
| 키리바시        | サ |
| 대한민국           | 구 |
| Kosovo          | XK |
| 쿠웨이트          | KW |
| 키르기스스탄      | KG |
| Laos            | 라 |
| 라트비아          | LV-LV&PLATFORM |
| 레바논         | 파운드 |
| 레소토         | LS |
| 라이베리아         | LR |
| 리비아           | 제대로 |
| 리히텐슈타인   | LI |
| 리투아니아       | 연한 |
| 룩셈부르크      | 째 |
| 마카오 특별 행정구       | MO |
| 마다가스카르      | MG |
| Malawi          | ~ |
| 말레이시아        | 내 |
| 몰디브        | MV |
| 말리            | ML |
| 몰타           | T |
| 마샬 군도 | MH |
| 마르티니크      | MQ |
| 모리타니      | MR-IN&PLATFORM |
| 모리셔스       | MU |
| .         | YT |
| 멕시코          | 멕시코 |
| Micronesia      | FM |
| 몰도바         | IL |
| 모나코          | MC |
| 몽골        | MN |
| 몬테네그로      | 알리지 |
| Montserrat      | LPM |
| 모로코         | M |
| Mozambique      | MZ |
| 미얀마         | 200 |
| 나미비아         | NA |
| Nauru           | 번호 |
| 네팔어           | NP-IN |
| 네덜란드     | NL |
| 뉴칼레도니아   | 도메인이 |
| 뉴질랜드     | NZ |
| 니카라과       | 니 |
| (또는)           | NE |
| 나이지리아         | 못하게 |
| Niue            | 누 |
| 노퍽 섬  | NF |
| 북한     | KP |
| 북쪽 마케도니아 | MK |
| 북마리아나 군도 | NP-IN |
| 노르웨이          | 아니요 |
| 오만            | OM |
| 파키스탄        | PK |
| Palau           | PW |
| 팔레스타인 자치 기관 | ICP |
| 파나마          | PA |
| 파푸아 New 기니 | PG |
| 파라과이        | PY |
| 페루            | 페 |
| 필리핀     | PH |
| 핏케언 군도 | PN |
| 폴란드          | PL |
| 포르투갈        | 18PT |
| 푸에르토리코     | PR |
| 카타르           | 대답 |
| 리유니언         | & |
| 루마니아         | RO |
| 러시아          | RU-RU&PLATFORM |
| 르완다          | RW |
| 사바            | XS |
| 세인트 Barthelemy | BL |
| 세인트 크리스토퍼 네비스 | KN |
| 세인트 루시아     | LC |
| 세인트 Martin    | MF |
| 생피에르앤드미클롱 | 시간은 |
| 세인트 빈센트 그레나딘 | VC |
| 사모아           | WS |
| 산마리노      | 김 |
| 상투메 상투메 및 프린시페 | ST |
| 사우디아라비아    | 사우디아라비아 |
| 세네갈         | 만들려면 |
| 세르비아          | R |
| 세      | SC |
| 시에라리온    | SL | 
| 싱가포르       | SG |
| 신 외  | E |
| 신 안틸레스    | SX |
| 슬로바키아        | SK-SK&PLATFORM |
| 슬로베니아        | SL |
| 솔로몬 군도 | SB |
| 소말리아         | 그렇다면 |
| 남아프리카 공화국    | 목차 |
| 사우스 조지아 및 사우스 샌드위치 군도 | EPG |
| 남 수단     | SS |
| 스페인           | 디자인이 |
| 스리랑카       | LK |
| 세인트 헬레나, 어센션, 트리스탄 다 쿠나 | SH |
| 수단           | 스트링을 |
| 수리남        | 않음 |
| 스발바르드        | SJ |
| 스웨덴          | 보내기 |
| 스위스     | CH |
| 시리아           | SY |
| 대만          | 얕은 |
| 키스탄      | TJ |
| 탄자니아        | TZ |
| 태국        | 제곱 |
| 동티모르-동티모르     | TL |
| Togo            | TG |
| Tokelau         | TK-TM&PLATFORM |
| 표준시           | 받는 사람 |
| 트리니다드 토바고 | TT-RU&PLATFORM |
| 튀니지         | TN-ZA&PLATFORM |
| 터키          | 비교한 |
| 투르크메니스탄    | M |
| 터크스 케이커스 제도 | TC |
| Tuvalu          | 텔레비전 |
| 미국 소수 외부 제도 | 다이얼 |
| 미국령 버진 아일랜드 | VI |
| 우간다          | UG-CN&PLATFORM |
| 우크라이나         | UA |
| 아랍 에미리트 연합국 | AE |
| 영국  | 26 |
| 미국   | 보세요 |
| 우루과이         | UY |
| 우즈베키스탄      | UZ |
| 바누아투         | VU |
| 바티칸 시티    | VA |
| 베네수엘라       | V |
| 베트남         | VN |
| 월리스 푸투나 | 에서도 |
| 예멘           | 하 |
| 잠비아          | ZM |
| 짐바브웨        | ZW |

