---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '요약: 비즈니스용 Skype 서버 2015 영구 채팅 서버를 배포 하는 방법을 알아보려면이 항목을 참조 하세요.'
ms.openlocfilehash: 4814d1c82c133ce0690a707bd96ccb377ed76203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794096"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 영구 채팅 서버 배포
 
**요약:** 비즈니스용 Skype 서버 2015 영구 채팅 서버를 배포 하는 방법을 알아보려면이 항목을 참조 하세요.
  
영구 채팅 서버를 배포 하려면 다음을 수행 합니다. 
  
- 토폴로지 작성기를 사용 하 여 배포 하려는 토폴로지와 구성 요소를 정의 하거나 가져오고 그 다음에 게시 합니다.
    
- 영구 채팅 서버 구성 요소를 배포 하기 위한 환경 준비
    
- 배포를 위해 영구 채팅 서버 구성 요소 설치 및 구성
    
영구 채팅 서버를 배포 하기 전에 [비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대 한 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)을 읽어야 합니다. 계획 항목에서는 하드웨어 및 소프트웨어 요구 사항, 가능 토폴로지 및 collocation 시나리오에 대해 설명 합니다. 
  
> [!NOTE] 
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요. 영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다. 

## <a name="deployment-checklist"></a>배포 검사 목록

하나 이상의 비즈니스용 Skype 서버 프런트 엔드 풀 또는 비즈니스용 Skype Standard Edition Server를 포함 하 여 초기 토폴로지를 배포한 후 영구 채팅 서버를 배포할 수 있습니다. 배포 검사 목록은 영구 채팅 서버를 배포 하는 데 필요한 기본 단계를 설명 하 고 자세한 내용은 링크를 제공 합니다.
  
**영구 채팅 서버 배포 프로세스**

|**작업**|**방법은**|**필요한 역할 및 그룹 구성원**|**관련 항목**|
|:-----|:-----|:-----|:-----|
|**필수 하드웨어 및 소프트웨어 설치** <br/> | 시스템 요구 사항을 충족 하는 하드웨어에서 다음을 설치 합니다. <br/>  영구 채팅 서버 프런트 엔드 서버에서 다음을 수행 합니다. <br/>  시스템 요구 사항을 충족 하는 운영 체제 <br/>  비즈니스용 Skype 서버를 실행 하는 컴퓨터의 소프트웨어 필수 구성 요소 <br/>  영구 채팅 서버 데이터베이스를 호스트할 서버에서 다음을 수행 합니다. <br/>  지원 되는 버전의 SQL Server <br/>  영구 채팅 서버 준수이 필요한 경우 다음을 수행 합니다. <br/>  영구 채팅 서버 준수 데이터베이스를 호스트 하는 서버의 SQL Server <br/> |로컬 관리자 그룹의 구성원 인 모든 사용자  <br/> |[비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [비즈니스용 Skype 서버 2015에 대한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**영구 채팅 서버를 지원 하기 위해 적절 한 내부 토폴로지 만들기 (및 선택적으로 지속적인 채팅 준수)** <br/> | 토폴로지 작성기를 실행 하 여 토폴로지에 영구 채팅 서버 풀을 추가 합니다. <br/>  토폴로지에 영구 채팅 서버 구성 요소 추가 <br/>  영구 채팅 서버 저장소에 대 한 SQL Server 데이터베이스 만들기 (및 재해 복구용 백업 SQL Server) <br/>  새로운 비즈니스용 Skype 파일 저장소를 정의 하거나 영구 채팅 서버 파일에 대 한 기존 비즈니스용 Skype 파일 저장소를 사용 합니다. <br/>  요청을 라우팅할 수 있는 비즈니스용 Skype 서버 풀을이 영구 채팅 서버 풀에 연결 <br/>  지속적인 채팅 준수이 필요한 경우: <br/>  영구 채팅 준수 스토어 추가 <br/>  준수를 사용 하도록 설정 하려면 영구 채팅 서버 풀 정의 확인란을 클릭 합니다. <br/>  토폴로지를 게시 합니다. <br/>  Standard Edition에 영구 채팅 서버를 설치 하는 경우 영구 채팅 서버 풀의 FQDN (정규화 된 도메인 이름)이 스탠더드 버전 서버와 일치 해야 하며, SQL Server 데이터베이스가 표준에 대 한 SQL Server Express 인스턴스에서 collocated 됩니다. 에디션 서버 <br/> |토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정입니다.  <br/> 토폴로지, 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 인 계정을 게시 하려면 사용자에 게 영구 채팅 서버 파일에 대 한 비즈니스용 Skype 파일 저장소에 대 한 전체 제어 권한 (읽기/쓰기/수정)이 있어야 합니다 (토폴로지 작성기가 필수 Dacl을 구성할 수 있도록).  <br/> |[비즈니스용 Skype 서버 2015에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md) <br/> [비즈니스용 Skype Server 2015 토폴로지에 영구 채팅 서버 추가](add-persistent-chat-server.md) <br/> |
|**영구적 채팅 서버 배포** <br/> | 영구 채팅 서버를 실행 하는 모든 컴퓨터에서 비즈니스용 Skype 서버 설정을 실행 합니다. 영구 채팅 서버 설정은 다음 지침을 제공 하는 비즈니스용 Skype 서버 배포 마법사에 통합 되어 있습니다. <br/>  로컬 관리 저장소 배포 <br/>  영구 채팅 서비스 설치 <br/>  인증서 요청 및 할당 <br/>  서비스 실행 및 시작 <br/> |로컬 관리자 그룹의 구성원 인 모든 사용자  <br/> |[비즈니스용 Skype 서버 2015에서 영구 채팅 서버 배포](deploy-persistent-chat-server.md) <br/> |
|**영구적 채팅 관리자 만들기** <br/> |CsPersistentChatAdministrator 보안 그룹에 사용자를 추가 합니다.  <br/> |도메인 관리자의 구성원 인 모든 사용자  <br/> |[영구 채팅 관리자 만들기](create-a-persistent-chat-administrator.md) <br/> |
|**영구 채팅 서버 구성** <br/> | 사용자 구성: <br/>  영구 채팅 서버에 액세스 하려면 정책에 따라 사용자를 설정 해야 합니다. 기본적으로 정책은 모든 사용자에 대해 해제 되며 전역/사이트/풀/사용자 범위에서 정의 될 수 있습니다. <br/>  설정 구성 <br/> |사용자는 CsPersistentChatAdministrator의 구성원 이어야 합니다. 정책을 변경 하려면 사용자가 적어도 CsUserAdministrator에 있어야 합니다.  <br/> |[비즈니스용 Skype 서버 2015에서 영구 채팅 서버 관리](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

