---
title: 비즈니스용 Skype 서버에서 영구 채팅 서버 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 2015 영구 채팅 서버를 배포하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830478"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버에서 영구 채팅 서버 배포
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2015 영구 채팅 서버를 배포하는 방법을 배워 읽습니다.
  
영구 채팅 서버를 배포하기 위해 다음을 실행합니다. 
  
- 토폴로지 작성기에서 배포할 토폴로지 및 구성 요소를 정의하거나 가져오고 이후에 게시합니다.
    
- 영구 채팅 서버 구성 요소 배포를 위한 환경 준비
    
- 배포를 위한 영구 채팅 서버 구성 요소 설치 및 구성
    
영구 채팅 서버를 배포하기 전에 비즈니스용 Skype 서버 [2015에서](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)영구 채팅 서버 계획을 읽어야 합니다. 계획 항목에서는 하드웨어 및 소프트웨어 요구 사항, 가능한 토폴로지 및 배포 시나리오에 대해 설명합니다. 
  
> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. Teams에서 동일한 기능을 사용할 수 있습니다. 자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here) 영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다. 

## <a name="deployment-checklist"></a>배포 검사 목록

하나 이상의 비즈니스용 Skype 서버 프런트 엔드 풀 또는 비즈니스용 Skype Standard Edition Server를 포함하여 초기 토폴로지 배포 후 영구 채팅 서버를 배포할 수 있습니다. 배포 검사 목록은 영구 채팅 서버를 배포하는 데 필요한 기본 단계를 설명하고 자세한 내용을 확인할 수 있는 링크를 제공합니다.
  
**영구 채팅 서버 배포 프로세스**

|**작업**|**단계**|**필수 역할 및 그룹 구성원 자격**|**관련 항목**|
|:-----|:-----|:-----|:-----|
|**하드웨어 및 소프트웨어 필수 구성 요소 설치** <br/> | 시스템 요구 사항을 충족하는 하드웨어에 다음을 설치합니다. <br/>  영구 채팅 서버 프런트 엔드 서버에서 다음을 실행합니다. <br/>  시스템 요구 사항을 충족하는 운영 체제 <br/>  비즈니스용 Skype 서버를 실행하는 컴퓨터의 소프트웨어 선행 구성 <br/>  영구 채팅 서버 데이터베이스를 호스팅할 서버에서 다음을 실행합니다. <br/>  지원되는 버전의 SQL Server <br/>  영구 채팅 서버 준수가 필요한 경우: <br/>  SQL Server 채팅 서버 준수 데이터베이스를 호스팅할 서버의 데이터 <br/> |로컬 Administrators 그룹의 구성원인 모든 사용자입니다.  <br/> |[비즈니스용 Skype 서버 2015에 대한 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [비즈니스용 Skype 서버 2015의 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항(비즈니스용 Skype 서버 2015)](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**영구 채팅 서버를 지원하는 적절한 내부 토폴로지 만들기(및 영구 채팅 준수(선택 사항)** <br/> | 토폴로지 작성기에서 영구 채팅 서버 풀을 토폴로지에 추가합니다. <br/>  토폴로지에 영구 채팅 서버 구성 요소 추가 <br/>  영구 채팅 SQL Server 데이터베이스 및 재해 복구를 위한 백업 SQL Server 만들기 <br/>  새 비즈니스용 Skype 파일 저장소 정의 또는 영구 채팅 서버 파일에 기존 비즈니스용 Skype 파일 저장소 사용 <br/>  이 영구 채팅 서버 풀로 요청을 라우팅할 수 있는 비즈니스용 Skype 서버 풀 연결 <br/>  영구 채팅 준수가 필요한 경우: <br/>  영구 채팅 준수 저장소 추가 <br/>  준수를 사용하도록 설정하려면 영구 채팅 서버 풀 정의 확인란을 클릭합니다. <br/>  토폴로지를 게시합니다. <br/>  Standard Edition에 영구 채팅 서버를 설치하는 경우 영구 채팅 서버 풀의 FQDN(정규화된 도메인 이름)이 Standard Edition 서버와 일치해야 합니다. SQL Server 데이터베이스는 Standard Edition 서버의 SQL Server Express 인스턴스에 함께 지정됩니다. <br/> |토폴로지, 즉 로컬 Users 그룹의 구성원인 계정을 정의합니다.  <br/> 토폴로지 게시를 위해서는 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정과 영구 채팅 서버 파일의 비즈니스용 Skype 파일 저장소에 대한 모든 권한(읽기/쓰기/수정)도 부여해야 합니다(토폴로지 작성기에서 필요한 DACL을 구성할 수 있도록).  <br/> |[비즈니스용 Skype 서버에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md) <br/> [영구 채팅 서버를 비즈니스용 Skype 서버 2015 토폴로지에 추가](add-persistent-chat-server.md) <br/> |
|**영구적 채팅 서버 배포** <br/> | 영구 채팅 서버를 실행하는 모든 컴퓨터에서 비즈니스용 Skype 서버 설정을 실행합니다. 영구 채팅 서버 설정은 다음 지침을 제공하는 비즈니스용 Skype 서버 배포 마법사에 통합됩니다. <br/>  로컬 관리 저장소 배포 <br/>  영구 채팅 서비스 설치 <br/>  인증서 요청 및 할당 <br/>  서비스 실행 및 시작 <br/> |로컬 Administrators 그룹의 구성원인 모든 사용자입니다.  <br/> |[비즈니스용 Skype 서버에서 영구 채팅 서버 배포](deploy-persistent-chat-server.md) <br/> |
|**영구적 채팅 관리자 만들기** <br/> |CsPersistentChatAdministrator 보안 그룹에 사용자를 추가합니다.  <br/> |도메인 관리자의 구성원인 모든 사용자입니다.  <br/> |[비즈니스용 Skype 서버에서 영구 채팅 관리자 만들기](create-a-persistent-chat-administrator.md) <br/> |
|**영구 채팅 서버 구성** <br/> | 사용자 구성: <br/>  영구 채팅 서버에 액세스하기 위해 정책을 통해 사용자를 사용하도록 설정해야 합니다. 기본적으로 정책은 모든 사용자에 대해 꺼져 있으며 전역/사이트/풀/사용자 범위에서 정의할 수 있습니다. <br/>  설정 구성 <br/> |사용자는 CsPersistentChatAdministrator의 구성원이 되어야 합니다. 정책을 변경하려면 최소한 사용자가 CsUserAdministrator에 있어야 합니다.  <br/> |[비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

