---
title: 연산자 커넥트
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 요구 사항 및 배포 계획과 커넥트 운영자에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694543"
---
# <a name="plan-for-operator-connect"></a>연산자에 대한 커넥트

>[!NOTE]
>연산자 커넥트 현재 공개 미리 보기에서만 **사용할 수 있습니다.** 공개 미리 보기를 사용하면 예정된 기능을 테스트하고 피드백을 제공할 수 있습니다. 공개 미리 보기에 포함된 기능은 완료되지 않을 수 있으며, 변경이 진행될 수 있으며, 클라우드에서 지원되지 Office 365 Government 있습니다.

운영자 커넥트 는 PSTN(공용 전환 전화 네트워크)에 연결 및 연결과 연결 Teams 전화 시스템.  

이 문서에서는 이점 및 요구 사항을 설명하고 운영자 프로그램에 참여하는 커넥트 나열합니다.  운영자 커넥트 조직에 적합한 솔루션으로 결정한 경우 이 문서를 [읽은](operator-connect-configure.md)후 연산자 커넥트.  

## <a name="benefits"></a>이점

연산자 커넥트 경우 기존 연산자가 Microsoft Operator 커넥트 프로그램에 참여하는 경우 PSTN 호출을 사용자에 가져오기 위한 서비스를 관리할 수 Teams. 연산자 커넥트 프로그램은 다음과 같은 이점을 제공합니다.

- **기존 계약을 활용하거나 새 연산자를 찾습니다.** 원하는 운영자 및 계약을 유지하거나, 비즈니스 요구 사항을 충족하기 위해 참여 연산자의 선택에서 새 연산자를 선택합니다.

- **운영자 관리 인프라입니다.** 운영자는 PSTN 호출 서비스 및 SBC(세션 테두리 컨트롤러)를 관리하므로 하드웨어 구매 및 관리를 저장할 수 있습니다.

- **더 빠르고 쉽게 배포할 수 있습니다.** 운영자에 빠르게 연결하고 사용자에 전화 번호를 할당할 수 있습니다. 모든 관리 센터에서 Teams 있습니다.

- **향상된 지원 및 안정성.** 운영자는 지원 서비스를 개선하기 위해 기술 지원 및 공유 서비스 수준 계약을 제공하고, Azure에서 제공하는 직접 피어링은 향상된 안정성을 위해 일대일 네트워크 연결을 만듭니다.

## <a name="requirements"></a>요구 사항

 운영자는 커넥트 경우 조직에 적합한 솔루션일 수 있습니다.

- Microsoft 통화 요금제는 지리적 위치에서 사용할 수 없습니다.
- 기본 설정 연산자는 Microsoft 연산자 커넥트 참여자입니다.
- 새 연산자를 찾아 통화에서 Teams.

연산자에서 전화 번호 할당을 사용하도록 설정하려면 커넥트 다음을 수행해야 합니다.

- Teams 전화 라이선스가 부여됩니다. 자세한 내용은 사용자에 대한 추가 [전화 시스템?](what-is-phone-system-in-office-365.md) 및 Teams 추가 기능 라이선스 할당 을 [참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- TeamsOnly 모드에서. 자세한 내용은 공존 및 상호 Microsoft Teams 비즈니스용 Skype 이해를 [참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="available-operators"></a>사용 가능한 연산자

다음 연산자는 Microsoft Operator 커넥트 참여자입니다.

| 연산자 | 기능 | 국가 범위 |
| --- | --- | --- |
| `BT`  | 통화 | 벨기에, 덴마크, 핀란드, 프랑스, 독일, 아일랜드, 이탈리아, 룩셈부르크, 네덜란드, 노르웨이, 폴란드, 남아프리카, 스페인, 스웨덴, 스위스, 영국 |
| `Intrado` | 통화 | 벨기에, 캐나다, 덴마크, 프랑스, 독일, 아일랜드, 룩셈부르크, 네덜란드, 스페인, 스웨덴, 영국, 미국  |
| `NTT`  | 통화 | 오스트리아, 벨기에, 브라질, 캐나다, 체코, 덴마크, 핀란드, 프랑스, 독일, 아일랜드, 이탈리아, 룩셈부르크, 멕시코, 네덜란드, 노르웨이, 폴란드, 포르투갈, 푸에르토리코, 루마니아, 남아프리카, 스페인, 스웨덴, 스위스, 영국, 미국 |
| `NuWave` | 통화 | 오스트리아, 벨기에, 캐나다, 덴마크, 프랑스, 독일, 아일랜드, 이탈리아, 네덜란드, 포르투갈, 스페인, 스웨덴, 스위스, 영국, 미국   |
| `Orange Business Services` | 통화 | 오스트리아, 벨기에, 체코, 덴마크, 핀란드, 프랑스, 프랑스령 기아나, 독일, 과들루페, 아일랜드, 이탈리아, 룩셈부르크, 마르티니크, 마요테, 네덜란드, 노르웨이, 폴란드, 포르투갈, 레위니온, 세인트 바르테레미, 세인트 마틴, 스페인, 스발바르, 스웨덴, 스위스, 영국  |
| `Pure IP` | 통화 | 오스트레일리아, 오스트리아, 벨기에, 브라질, 불가리아, 캐나다, 칠레, 콜롬비아, 크로아티아, 키프로스, 체코, 덴마크, 핀란드, 프랑스, 독일, 그리스, 홍콩 S.A.R., 아일랜드, 이탈리아, 일본, 리투아니아, 룩셈부르크, 말레이시아, 멕시코, 네덜란드, 뉴질랜드, 노르웨이, 파나마, 폴란드, 포르투갈, 푸에르토리코, 루마니아, 싱가포르, 슬로바키아, 슬로베니아, 남아프리카, 스페인, 스웨덴, 스위스, 영국, 미국  |
| `Rogers Business` | 통화 | 캐나다  |
| `TATA Communications` | 통화 | 오스트레일리아, 오스트리아, 벨기에, 캐나다, 체코, 덴마크, 프랑스, 독일, 홍콩 S.A.R., 헝가리, 아일랜드, 이탈리아, 말레이시아, 멕시코, 네덜란드, 뉴질랜드, 폴란드, 포르투갈, 루마니아, 싱가포르, 대한민국, 스페인, 스웨덴, 스위스, 태국, 영국, 미국 |
| `Telekom Deutschland` | 통화 | 독일  |
| `Telenor` | 통화 | 덴마크, 핀란드, 노르웨이, 스웨덴  |
| `Verizon` | 통화 | 미국 |
