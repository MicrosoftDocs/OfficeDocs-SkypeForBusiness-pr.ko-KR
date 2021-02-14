---
title: 직접 라우팅 국가 코드
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 최적의 미디어 경로를 선택할 수 있도록 이 문서를 읽고 직접 라우팅에 대한 미디어 경로 국가 코드를 찾습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69265e797b256186f714e2cd4dcefcb3751c05ee
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904810"
---
# <a name="direct-routing-media-path-country-codes"></a>직접 라우팅 미디어 경로 국가 코드

미디어에 대한 라우팅 경로를 선택할 때 직접 라우팅은 기본적으로 SBC(세션 테두리 컨트롤러)의 공용 IP 주소를 기반으로 항상 데이터 센터를 할당하고 항상 SBC 데이터 센터에 가장 가까운 경로를 선택합니다.

그러나 경우에 따라 기본 미디어 경로가 최적의 미디어 경로가 아 않을 수 있습니다. 예를 들어 미국 범위의 공용 IP는 유럽에 있는 SBC에 할당될 수 있습니다. 

New-CsOnlinePSTNGateway 및 Set-CsOnlinePSTNGateway cmdlet과 함께 -MediaRelayRoutingLocationOverride 매개 변수를 사용하여 미디어 트래픽에 대한 기본 지역을 지정할 수 있습니다. 예를 들어 다음 명령은 기본 지역이 독일이 된다고 지정합니다.

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -MediaRelayRoutingLocationOverride DE 

호출 로그에서 미디어 경로에 대한 데이터 센터의 기본 할당이 SBC 데이터 센터에 가장 가까운 경로를 사용하지 않는다는 것을 명확하게 나타내는 경우 이 매개 변수를 설정하는 것이 좋습니다. 
 
## <a name="country-code-reference-table"></a>국가 코드 참조 테이블

다음 표에서는 -MediaRelayRoutingLocationOverride 매개 변수에 대한 국가 코드 값을 보여줍니다.

| 국가         | 코드 
|-----------------|--------------------|
| 아프가니스탄     | AF |
| Aland Islands   | AX |
| 알바니아         | AL |
| 알제리         | DZ |
| 미국령 사모아  | AS |
| 안도라         | AD |
| 앙골라          | AO |
| 앵귈라        | AI |
| 남극 대륙      | AQ | 
| 앤티가 바부다 | AG |
| 아르헨티나       | AR |
| 아르메니아         | AM |
| 아루바           | AW |
| 오스트레일리아       | AU |
| 오스트리아         | AT |
| 아제르바이잔      | AZ |
| 바하마         | BS |
| 바레인         | BH |
| 방글라데시      | BD |
| 바베이도스        | BB |
| 벨로루시         | BY |
| 벨기에         | BE |
| 벨리즈          | BZ |
| 베냉           | BJ |
| 버뮤다         | BM |
| 부탄          | BT |
| 볼리비아         | BO |
| 보니어         | BQ |
| 보스니아 헤르체고비나 | BA |
| 보츠와나        | BW |
| 부베 섬   | BV |
| 브라질          | BR |
| 영국령 인도양 준주 | IO |
| 영국령 버진아일랜드 | VG |
| 브루나이          | BN |
| 불가리아        | BG |
| 부르키나파소    | BF |
| 부undi         | BI |
| 카보 Verde      | CV |
| 캄보디아        | KH |
| 카메룬        | CM |
| 캐나다          | CA |
| 케이맨 제도  | KY |
| 중앙 아프리카 공화국 | CF |
| Chad            | TD |
| 칠레           | CL |
| 중국           | CN |
| 크리스마스 섬 | CX |
| 코코스(켈링) 제도 | CC |
| 콜롬비아        | CO |
| 코모로         | KM |
| Congo           | CG |
| Congo(DRC)     | CD |
| 쿡 제도    | CK |
| 코스타리카      | CR |
| Cote d'Ivoire   | CI |
| 크로아티아         | HR |
| 쿠바            | CU |
| Curacao         | CW |
| 키프로스          | CY |
| 체코어         | CZ |
| 덴마크         | DK |
| 지부티        | DJ |
| 도미니카        | DM |
| 도미니카 공화국 | DO |
| 에콰도르         | EC |
| 이집트           | EG |
| 엘살바도르     | SV |
| 적도 기니 | GQ |
| 에리트레아         | ER |
| 에스토니아         | EE |
| 에스와티니        | SZ |
| 에티오피아        | ET |
| Falkland Islands | FK |
| 페로 제도   | FO |
| 피지            | FJ |
| 핀란드         | FI |
| 프랑스          | FR |
| 프랑스령 기아나   | GF |
| 프랑스령 폴리네시아 | PF |
| 프랑스 남부 지역 | TF |
| 가본           | GA |
| 감비아          | GM |
| 그루지야         | GE |
| 독일         | DE |
| 가나           | GH |
| 지브할타르       | GI |
| 그리스          | GR |
| 그린란드       | GL |
| 그레나다         | GD |
| 과들루프      | GP |
| 괌            | GU |
| 과테말라       | GT |
| 게르지        | GG |
| 기니          | GN |
| Guinea-Bissau   | GW |
| 가이아나          | GY |
| 아이티           | 안녕 |
| 하드섬 및 맥도널드 제도 | HM |
| 온두라스        | HN |
| 홍콩 특별 행정구   | HK |
| 헝가리         | HU |
| 아이슬란드         | IS |
| 인도           | IN |
| 인도네시아       | ID |
| 이란            | IR |
| 이라크            | IQ |
| 아일랜드         | IE |
| 맨 아일     | 메신저 |
| 이스라엘          | IL |
| 이탈리아           | IT |
| 자메이카         | JM |
| 얀마렌       | XJ |
| 일본           | JP |
| 저지          | JE |
| 요르단          | JO |
| 카자흐스탄      | KZ |
| 케냐           | KE |
| 키리바시        | KI |
| 대한민국           | KR |
| 코소보          | XK |
| 쿠웨이트          | KW |
| 키르기스스탄      | KG |
| 라오스            | LA |
| 라트비아          | LV |
| 레바논         | LB |
| 레소토         | LS |
| 라이베리아         | LR |
| 리비아           | LY |
| 리히텐슈타인   | LI |
| 리투아니아       | LT |
| 룩셈부르크      | LU |
| 마카오 SAR       | MO |
| 마다가스카르      | MG |
| 말라위          | MW |
| 말레이시아        | MY |
| 몰디브        | MV |
| 말리            | ML |
| 몰타           | MT |
| 마셜 제도 | MH |
| 마르티니크      | MQ |
| 모리타니아      | MR |
| 모리셔스       | MU |
| 마요트         | YT |
| 멕시코          | MX |
| 미크로네시아      | FM |
| 몰도바         | MD |
| 모나코          | MC |
| 몽골        | MN |
| 몬테네그로      | ME |
| 몬트세라트      | MS |
| 모로코         | MA |
| 모잠비크      | MZ |
| 미얀마         | MM |
| 나미비아         | NA |
| 나우루           | NR |
| 네팔           | NP |
| 네덜란드     | NL |
| 뉴칼레도니아   | NC |
| 뉴질랜드     | NZ |
| 니카라과       | NI |
| 니제르           | NE |
| 나이지리아         | NG |
| 니우에            | NU |
| 노폴크 섬  | NF |
| North Korea     | KP |
| 마케도니아 북부 | MK |
| 북마리아나 제도 | NP |
| 노르웨이          | 아니요 |
| 오만            | OM |
| 파키스탄        | PK |
| 팔라우           | PW |
| 팔레스타인 자치 정부 | PS |
| 파나마          | PA |
| 파푸아뉴기니 | PG |
| 파라과이        | PY |
| 페루            | PE |
| 필리핀     | PH |
| 피테언 제도 | PN |
| 폴란드          | PL |
| 포르투갈        | PT |
| 푸에르토리코     | PR |
| 카타르           | QA |
| 리유니언         | RE |
| 루마니아         | RO |
| 러시아          | RU |
| 르완다          | RW |
| 사바            | XS |
| 생바르테레미 | BL |
| 세인트 크리스토퍼 네비스 | KN |
| 세인트 루시아     | LC |
| 생마르탱    | MF |
| 생피에르 미케론 | PM |
| 세인트빈센트그레나딘 | VC |
| 사모아           | WS |
| 산마리노      | SM |
| 상토메 및 프리니페 | ST |
| 사우디아라비아    | SA |
| 세네갈         | SN |
| 세르비아          | RS |
| Seychelles      | SC |
| 시에라리온    | SL | 
| 싱가포르       | SG |
| 신트 Eustatius  | XE |
| 신트마르텐    | SX |
| 슬로바키아        | SK |
| 슬로베니아        | SL |
| 솔로몬 제도 | SB |
| 소말리아         | SO |
| 남아프리카 공화국    | ZA |
| 사우스 조지아 및 사우스 샌드위치 제도 | GS |
| 남수단     | SS |
| 스페인           | ES |
| 스리랑카       | LK |
| St Helena, Ascension, Tristan da Cunha | SH |
| 수단           | SD |
| 수리남        | SR |
| 스발바르        | SJ |
| 스웨덴          | SE |
| 스위스     | CH |
| 시리아           | SY |
| 대만          | TW |
| 타지키스탄      | TJ |
| 탄자니아        | TZ |
| 태국        | TH |
| Timor-Leste     | TL |
| 토고            | TG |
| 토켈라우         | TK |
| Tonga           | 받는 사람 |
| 트리니다드 토바고 | TT |
| 튀니지         | TN |
| 터키          | TR |
| 투르크메니스탄    | TM |
| 터크스 케이코스 제도 | TC |
| 투발루          | TV |
| 미국 아웃리어 제도 | UM |
| 미국령 버진아일랜드 | VI |
| 우간다          | UG |
| 우크라이나         | UA |
| 아랍에미리트 | AE |
| 영국  | GB |
| 미국   | 미국 |
| 우루과이         | UY |
| 우즈베키스탄      | UZ |
| 바누아투         | VU |
| 바티얀어시티    | VA |
| 베네수엘라       | VE |
| 베트남         | VN |
| Wallis and Futuna | WF |
| 예멘           | YE |
| 잠비아          | ZM |
| 짐바브웨        | ZW |

