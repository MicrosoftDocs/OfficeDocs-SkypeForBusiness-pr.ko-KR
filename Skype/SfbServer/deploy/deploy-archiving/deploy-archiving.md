---
title: 비즈니스용 Skype 서버용 보관 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버용 보관을 배포하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 32b25b373bd5399928d5e5eaed063c194942f697
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825218"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 보관 배포
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 보관을 배포하는 방법을 배워 읽습니다.
  
보관은 비즈니스용 Skype 서버 배포의 각 프런트 엔드 서버에 자동으로 설치되지만 초기 설정 및 구성 단계를 수행해야 사용할 수 있습니다. 시작하기 전에 비즈니스용 Skype 서버에서 보관 계획의 [개념에 익숙해야 합니다.](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="deployment-checklist"></a>배포 검사 목록

보관을 설정하는 방법은 선택하는 저장소 옵션에 따라 다를 수 있습니다. 
  
- 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용하는 경우 사용자에 대해 비즈니스용 Skype 서버 보관 정책을 구성할 필요가 없습니다. 대신 사서함이 보류된 In-Place Exchange에 있는 사용자에 대한 보관을 지원하도록 Exchange In-Place 보류 정책을 구성합니다. 이러한 정책을 구성하는 자세한 내용은 Exchange 제품 설명서를 참조하십시오.
    
- 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용하지 않는 경우 비즈니스용 Skype 서버 보관 데이터베이스(SQL Server 데이터베이스)를 토폴로지에 추가하고 업데이트된 토폴로지를 게시한 다음 사용자에 대한 보관 정책 및 설정을 구성해야 합니다. 보관 데이터베이스는 초기 토폴로지 배포와 동시에 배포하거나 하나 이상의 프런트 엔드 풀 또는 Standard Edition Server를 배포한 후에 배포할 수 있습니다. 이 문서에서는 보관 데이터베이스를 기존 배포에 추가하여 배포하는 방법에 대해 설명합니다.
    
한 프런트 엔드 풀 또는 Standard Edition Server에서 보관을 사용하도록 설정하는 경우 배포의 다른 모든 프런트 엔드 풀 및 Standard Edition Server에 대해 보관을 사용하도록 설정해야 합니다. 통신을 보관해야 하는 사용자가 다른 풀에서 호스팅되는 그룹 IM 대화 또는 모임에 초대될 수 있기 때문입니다. 대화 또는 모임이 호스팅되는 풀에 보관이 설정되어 있지 않으면 전체 세션이 보관되지 않을 수 있습니다. 이러한 경우 보관이 설정된 사용자의 IM은 보관할 수 있지만 회의 콘텐츠 파일 및 회의 입장 또는 퇴장 이벤트가 보관되지 않습니다.
  
> [!IMPORTANT]
> 규정 준수를 위해 조직에서 보관이 중요한 경우 해당 사용자를 비즈니스용 Skype 서버에 사용하도록 설정하기 전에 보관을 배포하고, 정책 및 기타 옵션을 적절한 수준에서 구성한 다음 적절한 모든 사용자에 대해 보관을 설정해야 합니다. 
  
다음 표에서는 기존 토폴로지에 보관을 배포하는 데 필요한 단계에 대한 개요를 제공합니다.
  
|**작업 단계**|**단계**|**역할 및 그룹 구성원 자격**|**설명서**|
|:-----|:-----|:-----|:-----|
|**하드웨어 및 소프트웨어 필수 구성 요소 설치** <br/> |일부 또는 모든 사용자의 보관 저장소에 Exchange를 사용하여 Microsoft Exchange 통합을 사용하려면 기존 Exchange 배포가 필요합니다.  <br/> 일부 또는 모든 사용자에 대해 보관 저장소에 별도의 보관 데이터베이스(SQL Server 데이터베이스 사용)를 사용하려면 보관 데이터를 SQL Server 서버에 저장해야 합니다.  <br/> 보관은 엔터프라이즈 풀의 프런트 엔드 서버 및 Standard Edition Server에서 실행됩니다. 이러한 서버를 설치하는 데 필요한 것 외에 추가 하드웨어 또는 소프트웨어 요구 사항은 없습니다.  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |[비즈니스용 Skype 서버 2015에 대한 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [비즈니스용 Skype 서버 2015의 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [비즈니스용 Skype 및 Exchange 통합 계획](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[비즈니스용 Skype 서버 2019의 시스템 요구 사항](../../../SfBServer2019/plan/system-requirements.md) |
|**보관을 지원하는 적절한 내부 토폴로지 만들기(배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용하지 않는 경우만 해당)** <br/> |토폴로지 작성기에서 비즈니스용 Skype 서버 보관 데이터베이스(SQL Server 데이터베이스)를 토폴로지에 추가한 다음 토폴로지 게시  <br/> |보관 데이터베이스를 통합할 토폴로지(로컬 사용자 그룹의 구성원인 계정)를 정의합니다.  <br/> 토폴로지 게시를 위해 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정으로, 비즈니스용 Skype 서버 파일 저장소에 사용할 파일 공유에 대한 모든 권한(읽기/쓰기/수정)이 있는 계정(토폴로지 작성기에서 필요한 DACL을 구성할 수 있도록)  <br/> |[비즈니스용 Skype 서버에서 기존 배포에 보관 데이터베이스 추가](add-archiving-databases.md) <br/> |
|**서버 대 서버 인증 구성(Microsoft Exchange 통합을 사용하는 경우만 해당)** <br/> |비즈니스용 Skype 서버와 Exchange 간에 인증을 사용하도록 서버를 구성합니다. 보관을 사용하도록 설정하기 **전에 Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster를** 실행하여 Exchange 보관 저장소 연결의 유효성을 검사하는 것이 좋습니다. <br/> |서버에서 인증서를 관리하기 위한 적합한 권한이 있는 계정  <br/> |서버 대 서버 인증 관리  <br/> |
|**보관 옵션 및 정책 구성** <br/> |Microsoft Exchange 통합, 글로벌 정책 및 사이트 및 사용자 정책(모든 데이터 저장소에 Microsoft Exchange 통합을 사용하지 않는 경우)을 사용할지 여부와 중요 모드, 데이터 내보내기 및 제거와 같은 특정 보관 옵션을 포함하여 보관을 구성합니다.  <br/> Microsoft Exchange 통합을 사용하는 경우 Exchange In-Place 정책을 적절하게 구성합니다.  <br/> |RTCUniversalServerAdmins 그룹(Windows PowerShell만) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 지정  <br/> |[비즈니스용 Skype 서버에 대한 보관 옵션 구성](configure-archiving-options.md) <br/> Exchange 제품 설명서(Microsoft Exchange 통합을 사용하는 경우).  <br/> |
   

