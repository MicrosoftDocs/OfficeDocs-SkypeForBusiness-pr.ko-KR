---
title: 비즈니스용 Skype 서버 제어판의 첫 번째 실행 검사 목록
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: 비즈니스용 Skype 서버 관리 및 관리를 위한 웹 기반 사용자 인터페이스인 비즈니스용 Skype 서버 제어판을 시작하세요. 제어판을 사용하여 이전 릴리스의 Microsoft Management Console을 사용하여 수행된 관리 작업 유형을 수행할 수 있습니다.
ms.openlocfilehash: 74c1d4ae7b9ed65932acf5b8491a2cd00c67831c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804898"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판의 첫 번째 실행 검사 목록

비즈니스용 Skype 서버 관리 및 관리를 위한 웹 기반 사용자 인터페이스인 비즈니스용 Skype 서버 제어판을 시작하세요. 제어판을 사용하여 이전 릴리스의 Microsoft Management Console을 사용하여 수행된 관리 작업 유형을 수행할 수 있습니다.

비즈니스용 Skype 서버를 배포한 후 수행하는 것이 좋습니다. 이러한 작업 중 일부는 배포 중에 이미 수행한 초기 구성 단계인 반면 다른 작업은 배포 또는 기본 설정 중에 구성한 설정의 구체화 또는 수정입니다. 이 항목에서 설명하는 다른 작업은 배포 프로세스 중에 수행한 구성의 유효성을 검사합니다.

> [!NOTE]
> 다음 표의 작업을 수행하기 전에 역할 기반 액세스 제어 항목의 "역할 및 범위" 섹션에 설명된 올바른 사용자 권한, 사용 권한 및 역할을 사용하여 로그온해야 [합니다.](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)

## <a name="first-run-checklist"></a>첫 실행 검사 목록

이 항목에서 설명하는 작업을 검토한 다음 조직에서 Lync Server 배포에 적합한 절차를 수행하는 것이 좋습니다.

|**작업**|**제어판 그룹**|**설명서**|
|:-----|:-----|:-----|
|토폴로지에서 설치한 서비스가 예상대로 실행되고 있는지 확인합니다.  <br/> |**토폴로지** <br/> |[서비스에 대한 세부 정보 보기](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|사용자가 비즈니스용 Skype 서버를 사용할 수 있도록 설정 선택적으로 이전 릴리스에서 마이그레이션하는 경우 사용자를 비즈니스용 Skype 서버로 이동하십시오.  <br/> |**사용자** <br/> |[사용자 관리](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|배포하거나 배포하려는 Enterprise Voice PSTN(전화망)에 대한 연결을 사용하도록 SIP 트렁크 연결을 구성합니다.  <br/> |**음성 라우팅** <br/> |[트렁크 및 변환 규칙 구성](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|배포한 Enterprise Voice 라우팅 Enterprise Voice 확인합니다.  <br/> |**음성 라우팅** <br/> |[음성 라우팅 테스트](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|보관 서버를 배포한 경우 보관 정책 및 설정이 조직의 규정 준수 요구 사항을 충족하는지 확인합니다.  <br/> |**모니터링 및 보관** <br/> |[보관 관리](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|모니터링 서버를 배포한 경우 모니터링 서버 보고서를 보고 사용 현황 및 진단 정보를 볼 수 있습니다.  <br/> |**홈** <br/> |[비즈니스용 Skype 서버 2015에서 상태 및 모니터링 관리](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


