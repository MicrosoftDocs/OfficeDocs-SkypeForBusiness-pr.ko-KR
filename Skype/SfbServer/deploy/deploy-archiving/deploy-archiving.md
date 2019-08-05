---
title: 비즈니스용 Skype Server에 대 한 아카이빙 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '요약: 비즈니스용 Skype 서버용 보관을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 813911dba5bfc662ee1c6bea9dab99e34c031e98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190485"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>비즈니스용 Skype Server에 대 한 아카이빙 배포
 
**요약:** 비즈니스용 Skype 서버용 보관을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
비즈니스용 Skype Server 배포의 각 프런트 엔드 서버에 보관이 자동으로 설치 되지만, 먼저 초기 설정 및 구성 단계를 수행 해야 사용할 수 있습니다. 시작 하기 전에 [비즈니스용 Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)의 개념을 잘 알고 있어야 합니다.
  
## <a name="deployment-checklist"></a>배포 검사 목록

보관을 설정 하는 방법은 어떤 저장소 옵션을 선택 하느냐에 따라 달라 집니다. 
  
- 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자 용 비즈니스용 Skype Server 보관 정책을 구성할 필요가 없습니다. 대신 Exchange에 있는 사용자의 보관을 지원 하도록 Exchange 원본 위치 유지 정책을 구성 하면 해당 사서함이 원본 위치 유지에 배치 됩니다. 이러한 정책을 구성 하는 방법에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하세요.
    
- 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우 비즈니스용 Skype Server 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 업데이트 된 토폴로지를 게시 한 다음 보관 정책을 구성 하 고 다음을 수행 해야 합니다. 사용자에 대 한 설정입니다. 초기 토폴로지를 배포 하거나 적어도 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 배포한 후에는 보관 데이터베이스를 배포할 수 있습니다. 이 문서에서는 보관 데이터베이스를 기존 배포에 추가 하 여 배포 하는 방법을 설명 합니다.
    
프런트 엔드 풀 또는 Standard Edition 서버 중 하나에서 보관을 사용 하도록 설정 하는 경우 배포의 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에 대해이 기능을 사용 하도록 설정 해야 합니다. 이는 통신을 보관 해야 하는 사용자가 다른 풀에서 호스트 되는 그룹 메신저 대화 또는 모임에 초대 될 수 있기 때문입니다. 대화 또는 모임이 호스팅되는 풀에서 보관을 사용할 수 없는 경우 전체 세션이 보관 되지 않을 수 있습니다. 이러한 경우에는 보관을 사용 하는 사용자를 포함 한 메신저 대화를 계속 보관할 수 있지만 회의 콘텐츠 파일 및 회의 참가 또는 종료 이벤트는 보관이 불가능 합니다.
  
> [!IMPORTANT]
> 조직에서 규정 준수를 위해 보관 하는 것이 중요 한 경우에는 보관을 배포 하 고 적절 한 수준에서 정책 및 기타 옵션을 구성한 다음 모든 해당 사용자에 대해 보관을 설정 해야 합니다. 비즈니스 서버. 
  
다음 표에서는 기존 토폴로지에서 보관을 배포 하는 데 필요한 단계에 대해 간략하게 설명 합니다.
  
|**단계의**|**방법은**|**역할 및 그룹 구성원**|**설명서**|
|:-----|:-----|:-----|:-----|
|**필수 하드웨어 및 소프트웨어 설치** <br/> |Exchange를 사용 하 여 일부 또는 모든 사용자에 대해 저장소를 보관 하는 Microsoft Exchange 통합을 사용 하려면 기존 Exchange 배포가 필요 합니다.  <br/> SQL Server 데이터베이스를 사용 하 여 별도의 보관 데이터베이스를 사용 하 여 보관 데이터를 저장 하는 서버의 SQL Server 인 일부 또는 모든 사용자에 대해 저장소를 보관 합니다.  <br/> 보관은 엔터프라이즈 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 실행 됩니다. 해당 서버를 설치 하는 데 필요한 사항 외에 추가 하드웨어 또는 소프트웨어 요구 사항이 없습니다.  <br/> |로컬 관리자 그룹의 구성원 인 도메인 사용자입니다.  <br/> |[비즈니스용 Skype 서버 2015의 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [비즈니스용 Skype 서버 2015에 대한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [비즈니스용 Skype 서버 2015와 Exchange 통합 계획](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[비즈니스용 Skype 서버 2019에 대 한 시스템 요구 사항](../../../SfBServer2019/plan/system-requirements.md) |
|**보관을 지원 하기 위해 적절 한 내부 토폴로지 만들기 (배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에만 해당)** <br/> |토폴로지 작성기를 실행 하 여 비즈니스용 Skype Server 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가한 다음 토폴로지를 게시 합니다.  <br/> |보관 데이터베이스를 통합 하는 토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정입니다.  <br/> 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 인 계정이 며 비즈니스용 Skype Server 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있는 경우 토폴로지를 게시 하려면 작성기에서 필수 Dacl을 구성할 수 있습니다.  <br/> |[비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가](add-archiving-databases.md) <br/> |
|**서버 간 인증 구성 (Microsoft Exchange 통합을 사용 하는 경우에만 해당)** <br/> |비즈니스용 Skype 서버와 Exchange 간의 인증을 사용 하도록 서버를 구성 합니다. 보관을 사용 하도록 설정 하기 전에 **Test-CsExchangeStorageConnectivity Testuser_sipUri 폴더 Dumpster** 를 실행 하 여 Exchange 보관 저장소 연결을 확인 하는 것이 좋습니다. <br/> |서버에서 인증서를 관리 하기 위한 적절 한 사용 권한이 있는 계정입니다.  <br/> |서버 간 인증 관리  <br/> |
|**보관 옵션 및 정책 구성** <br/> |Microsoft Exchange 통합, 전역 정책, 모든 사이트 및 사용자 정책 (모든 데이터 저장소에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우), 특정 보관 옵션 (예: 중요 모드 및 데이터)을 포함 하 여 보관을 구성 합니다. 내보내기를 제거 합니다.  <br/> Microsoft Exchange 통합을 사용 하는 경우 Exchange 원본 위치 유지 정책을 적절 하 게 구성 합니다.  <br/> |RTCUniversalServerAdmins 그룹 (Windows PowerShell에만 해당) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 할당할 수 있습니다.  <br/> |[비즈니스용 Skype 서버에 대 한 보관 옵션 구성](configure-archiving-options.md) <br/> Exchange 제품 설명서 (Microsoft Exchange 통합을 사용 하는 경우)  <br/> |
   

