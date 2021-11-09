---
title: 보관을 위한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '요약: 이 항목을 통해 보관을 배포하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: bdf0e6fe170371d1596fd556450fca14d6433239
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837420"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>보관을 위한 비즈니스용 Skype 서버
 
**요약:** 이 항목을 통해 보관을 배포하는 방법을 비즈니스용 Skype 서버.
  
보관은 비즈니스용 Skype 서버 배포의 각 프런트 엔드 서버에 자동으로 설치되지만 초기 설정 및 구성 단계를 수행해야만 보관을 사용할 수 있습니다. 시작하기 전에 Plan [for archiving in 비즈니스용 Skype 서버.](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="deployment-checklist"></a>배포 검사 목록

보관을 설정하는 방법은 선택하는 저장소 옵션에 따라 다를 수 있습니다. 
  
- 배포의 Exchange Microsoft Exchange 통합을 사용하는 경우 사용자에 대한 비즈니스용 Skype 서버 정책을 구성할 필요가 없습니다. 대신 사서함이 Exchange In-Place 보류에 Exchange 사용자의 보관을 지원하도록 In-Place 구성합니다. 이러한 정책을 구성하는 자세한 내용은 제품 설명서의 Exchange 참조하십시오.
    
- 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용하지 않는 경우 비즈니스용 Skype 서버 보관 데이터베이스(SQL Server 데이터베이스)를 토폴로지에 추가하고, 업데이트된 토폴로지 를 게시한 다음 사용자에 대한 보관 정책 및 설정을 구성해야 합니다. 보관 데이터베이스를 초기 토폴로지 배포와 동시에 배포하거나 하나 이상의 프런트 엔드 풀 또는 서버 Standard Edition 배포할 수 있습니다. 이 문서에서는 보관 데이터베이스를 기존 배포에 추가하여 배포하는 방법에 대해 설명합니다.
    
한 프런트 엔드 풀 또는 Standard Edition 서버에서 보관을 사용하도록 설정하는 경우 배포의 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에 대해 보관을 사용하도록 설정해야 합니다. 통신을 보관해야 하는 사용자가 다른 풀에서 호스팅되는 그룹 IM 대화 또는 모임에 초대될 수 있기 때문입니다. 대화 또는 모임이 호스팅되는 풀에 보관이 설정되어 있지 않으면 전체 세션이 보관되지 않을 수 있습니다. 이러한 경우 보관이 설정된 사용자의 IM은 보관할 수 있지만 회의 콘텐츠 파일 및 회의 입장 또는 퇴장 이벤트가 보관되지 않습니다.
  
> [!IMPORTANT]
> 규정 준수를 위해 조직에서 보관이 중요한 경우 보관을 배포하고 정책 및 기타 옵션을 적절한 수준에서 구성한 다음 모든 해당 사용자에 대해 보관을 설정한 후 해당 사용자가 보관을 사용하도록 설정해야 비즈니스용 Skype 서버. 
  
다음 표에서는 기존 토폴로지에 보관을 배포하는 데 필요한 단계에 대한 개요를 제공합니다.
  
|**작업 단계**|**단계**|**역할 및 그룹 구성원 자격**|**설명서**|
|:-----|:-----|:-----|:-----|
|**하드웨어 및 소프트웨어 필수 구성 요소 설치** <br/> |Microsoft Exchange 통합(일부 Exchange 또는 모든 사용자의 보관 저장소에 사용)을 사용하려면 기존 Exchange 배포해야 합니다.  <br/> 일부 또는 모든 사용자에 대해 보관 저장소에 별도의 보관 데이터베이스(SQL Server 사용)를 사용하려면 보관 데이터를 SQL Server 서버에 저장해야 합니다.  <br/> 보관은 Enterprise 서버의 프런트 엔드 서버에서 Standard Edition 실행됩니다. 이러한 서버를 설치하는 데 필요한 것 외에 추가 하드웨어 또는 소프트웨어 요구 사항은 없습니다.  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |[비즈니스용 Skype 서버 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015년 비즈니스용 Skype 서버 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [비즈니스용 Skype 및 Exchange 통합 계획](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[2019년 비즈니스용 Skype 서버 시스템 요구 사항](../../../SfBServer2019/plan/system-requirements.md) |
|**보관을 지원하는 적절한 내부 토폴로지 만들기(배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용하지 않는 경우만 해당)** <br/> |토폴로지 작성기 를 실행하여 비즈니스용 Skype 서버(SQL Server 데이터베이스)를 토폴로지에 추가한 다음 토폴로지 게시합니다.  <br/> |보관 데이터베이스를 통합할 토폴로지(로컬 사용자 그룹의 구성원인 계정)를 정의합니다.  <br/> 토폴로지 게시를 위해 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정으로, 비즈니스용 Skype 서버 파일 저장소에 사용할 파일 공유에 대한 모든 권한(읽기/쓰기/수정)이 있는 계정(토폴로지 작성기에서 필요한 DACL을 구성할 수 있도록)  <br/> |[보관 데이터베이스를 기존 배포에 비즈니스용 Skype 서버](add-archiving-databases.md) <br/> |
|**서버 대 서버 인증 구성(Microsoft Exchange 통합을 사용하는 경우만 해당)** <br/> |서버와 서버 간에 인증을 사용하도록 비즈니스용 Skype 서버 Exchange. 보관을 사용하도록 설정하기 전에 testuser_sipUri 저장소 연결의 유효성을 검사하기 위해 **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dump Exchange ster를** 실행하는 것이 좋습니다. <br/> |서버에서 인증서를 관리하기 위한 적합한 권한이 있는 계정  <br/> |서버 대 서버 인증 관리  <br/> |
|**보관 옵션 및 정책 구성** <br/> |Microsoft Exchange 통합, 글로벌 정책 및 사이트 및 사용자 정책(모든 데이터 저장소에 대해 Microsoft Exchange 통합을 사용하지 않는 경우) 및 중요 모드, 데이터 내보내기 및 제거와 같은 특정 보관 옵션을 포함하여 보관을 구성합니다.  <br/> Microsoft Exchange 통합을 사용하는 경우 Exchange In-Place 보류 정책을 적절하게 구성합니다.  <br/> |RTCUniversalServerAdmins 그룹(Windows PowerShell만) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 지정  <br/> |[사용자에 대한 보관 옵션 비즈니스용 Skype 서버](configure-archiving-options.md) <br/> Exchange 설명서(Microsoft Exchange 통합을 사용하는 경우).  <br/> |
   

