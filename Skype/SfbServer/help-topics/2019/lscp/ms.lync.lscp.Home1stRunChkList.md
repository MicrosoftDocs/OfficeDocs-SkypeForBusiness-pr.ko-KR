---
title: 비즈니스용 Skype 서버 제어판에 대한 첫 번째 실행 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버의 관리 및 관리를 위한 웹 기반 사용자 인터페이스인 비즈니스용 Skype 서버 제어판에 오신 것을 환영 합니다. 제어판을 사용하면 이전 릴리스의 Microsoft Management Console을 사용하여 수행했던 다양한 유형의 관리 작업을 수행할 수 있습니다.
ms.openlocfilehash: 1f3241d854a402036832468594c2e399eb7b1617
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190899"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판에 대한 첫 번째 실행 검사 목록

비즈니스용 Skype 서버의 관리 및 관리를 위한 웹 기반 사용자 인터페이스인 비즈니스용 Skype 서버 제어판에 오신 것을 환영 합니다. 제어판을 사용하면 이전 릴리스의 Microsoft Management Console을 사용하여 수행했던 다양한 유형의 관리 작업을 수행할 수 있습니다.

비즈니스용 Skype 서버를 구축한 후에는 몇 가지 중요 한 작업을 수행 하는 것이 좋습니다. 이러한 작업 중 일부는 배포하는 동안 이미 수행했을 수 있는 초기 구성 단계이고, 나머지 다른 작업은 배포 또는 기본 설정에서 구성한 설정을 구체화하거나 수정하는 작업입니다. 이 항목에 설명되어 있는 다른 작업에서는 배포 프로세스에서 수행한 구성을 확인합니다.

> [!NOTE]
> 다음 표에 나와 있는 작업을 수행하기 전에 [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) 항목의 "역할 및 범위" 섹션에 설명된 대로 올바른 사용자 권한 및 역할을 사용하여 로그온했는지 확인합니다.

## <a name="first-run-checklist"></a>첫 번째 실행 검사 목록

이 항목에서 참조 하는 작업을 검토 한 다음 조직의 배포에 적합 한 절차를 수행 하는 것이 좋습니다.

|**작업**|**제어판 그룹**|**설명서**|
|:-----|:-----|:-----|
|토폴로지에 설치된 서비스가 제대로 실행되고 있는지 확인합니다.  <br/> |**토폴로지** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|비즈니스용 Skype 서버에서 사용자를 사용 하도록 설정 합니다. 필요에 따라 이전 릴리스에서 마이그레이션하는 경우 비즈니스용 Skype 서버로 사용자를 이동 합니다.  <br/> |**사용자** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Enterprise Voice를 배포했거나 배포하려는 경우 SIP 트렁크 연결을 구성하여 공중 전화망(PSTN)에 대한 연결을 사용하도록 설정합니다.  <br/> |**음성 라우팅** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Enterprise Voice를 배포한 경우 Enterprise Voice 라우팅 설정을 확인합니다.  <br/> |**음성 라우팅** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|보관 서버를 배포한 경우 보관 정책 및 설정이 조직의 준수 요구 사항을 충족하는지 확인합니다.  <br/> |**모니터링 및 보관** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|모니터링 서버를 배포한 경우 모니터링 서버 보고서에서 사용 및 진단 정보를 확인합니다.  <br/> |**홈** <br/> |[비즈니스용 Skype 서버에서 상태 및 모니터링 관리](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


