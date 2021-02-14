---
title: Skype for Busines 스트레스 및 성능 도구의 선행 작업 및 설정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구의 요구 사항 또는 선행 조건 스트레스 및 성능 도구를 설치하거나 설정하는 방법
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814958"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Skype for Busines 스트레스 및 성능 도구의 선행 작업 및 설정
 
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구의 요구 사항 또는 선행 조건 스트레스 및 성능 도구를 설치하거나 설정하는 방법
  
스트레스 및 성능 도구를 실행하기 전에 알고 있어야 하는 하드웨어, 소프트웨어 및 시스템 구성 요구 사항에 대한 다음 섹션이 있습니다.
  
- [클라이언트 하드웨어 요구 사항](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [클라이언트 소프트웨어 요구 사항](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [구성 요구 사항](prerequisites-and-setup.md#ConfigReqs)
    
또한 비즈니스용 Skype 서버 [2015](prerequisites-and-setup.md#Installing) 스트레스 및 성능 도구 설치에 대한 섹션도 있습니다.
  
## <a name="client-hardware-requirements"></a>클라이언트 하드웨어 요구 사항
<a name="ClientHardwareReqs"> </a>

비즈니스용 Skype 서버 2015 배포에 대해 스트레스 및 성능 도구를 실행하는 경우 테스트에서 4500명마다 다음 하드웨어 요구 사항을 충족해야 합니다.
  
- 1기가비트 네트워크 어댑터
    
- 8GB RAM
    
- 듀얼 코어 프로세서 2개
    
## <a name="client-software-requirements"></a>클라이언트 소프트웨어 요구 사항
<a name="ClientSoftwareReqs"> </a>

스트레스 및 성능 도구에 대해 지원되는 운영 체제는 다음입니다.
  
- Windows Server 2012
    
- Windows Server 2008(64비트)
    
또한 컴퓨터는 다음 소프트웨어 요구 사항을 충족해야 합니다.
  
- Microsoft .NET 4.5 Framework를 설치해야 합니다. [여기에서 .Net 4.5 Framework를 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Windows에서 데스크톱 환경 기능을 사용하도록 설정해야 합니다.
    
- Microsoft Visual C++ 2013(x64)이 설치되어야 합니다. [여기에서 Visual C++ 2013 다운로드](https://www.microsoft.com/download/details.aspx?id=40784)
    
- 비즈니스용 Skype 서버 2015를 성공적으로 배포해야 합니다.
    
## <a name="configuration-requirements"></a>구성 요구 사항
<a name="ConfigReqs"> </a>

스트레스 및 성능 도구를 성공적으로 실행하려면 다음 추가 구성이 필요합니다.
  
- 도메인 또는 로컬 관리자 그룹의 구성원으로 서버에 로그인해야 합니다.
    
- 비즈니스용 Skype 서버 2015 사용자 만들기 도구(UserProvisioningTool.exe)는 사용자 계정이 있는 프런트 엔드 서버 또는 Standard Edition 서버에 설치할 수 없습니다.
    
- 사용자 만들기 도구를 여러 번 실행하면 Microsoft Unified Communications를 사용할 수 있는 각 사용자에게 고유한 전화 번호가 필요합니다.
    
- 페이지 파일 크기는 시스템을 관리해야 합니다. 그렇지 않으면 컴퓨터 시스템의 RAM 양보다 1.5배 이상 커야 합니다.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 설치
<a name="Installing"> </a>

설치가 더 간단할 수 없습니다. 사용자 트래픽을 시뮬레이트하는 **데** 사용할 각 클라이언트 컴퓨터와 사용자 및 연락처를 만들 각 풀의 프런트 엔드 서버에서 Windows Installer 파일(CapacityPlanningTool.msi)을 실행해야 합니다.
  
다른 문서에 언급된 예제 스크립트와 함께 .msi를 다운로드하려면 다운로드 센터 링크(비즈니스용 [Skype 서버 2015, 스트레스 및 성능 도구)로 이동하세요.](https://www.microsoft.com/download/details.aspx?id=50367)
  

