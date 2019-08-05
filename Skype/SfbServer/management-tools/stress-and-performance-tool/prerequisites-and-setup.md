---
title: 명함 스트레스 및 성능 도구에 대 한 필수 구성 요소 및 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 요구 사항 또는 필수 구성 요소. 스트레스 및 성능 도구를 설치 하거나 설정 하는 방법을 설명 합니다.
ms.openlocfilehash: 37aa89a0e6158b4623711ded8752eab2eb9d77ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197026"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>명함 스트레스 및 성능 도구에 대 한 필수 구성 요소 및 설정
 
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 요구 사항 또는 필수 구성 요소. 스트레스 및 성능 도구를 설치 하거나 설정 하는 방법을 설명 합니다.
  
스트레스 및 성능 도구를 실행 하기 전에 알아야 할 하드웨어, 소프트웨어 및 시스템 구성 요구 사항에 대 한 다음과 같은 섹션이 있습니다.
  
- [클라이언트 하드웨어 요구 사항](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [클라이언트 소프트웨어 요구 사항](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [구성 요구 사항](prerequisites-and-setup.md#ConfigReqs)
    
또한 [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 설치](prerequisites-and-setup.md#Installing) 하는 방법도 나와 있습니다.
  
## <a name="client-hardware-requirements"></a>클라이언트 하드웨어 요구 사항
<a name="ClientHardwareReqs"> </a>

비즈니스용 Skype Server 2015 배포에 대해 스트레스 및 성능 도구를 실행할 때, 테스트의 모든 4500 사용자에 대해 최소한 다음 하드웨어 요구 사항이 충족 되어야 합니다.
  
- 1 기가 비트 네트워크 어댑터
    
- 8GB RAM
    
- 2 개의 듀얼 코어 Cpu
    
## <a name="client-software-requirements"></a>클라이언트 소프트웨어 요구 사항
<a name="ClientSoftwareReqs"> </a>

스트레스 및 성능 도구에 대해 지원 되는 운영 체제는 다음과 같습니다.
  
- Windows Server 2012
    
- Windows Server 2008 (64 비트)
    
또한 컴퓨터는 다음 소프트웨어 요구 사항을 충족 해야 합니다.
  
- Microsoft .NET 4.5 Framework가 설치 되어 있어야 합니다. [여기에서 .Net 4.5 프레임 워크를 다운로드 하세요.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- Windows에서 데스크톱 경험 기능이 설정 되어 있어야 합니다.
    
- Microsoft Visual c + + 2013 (x64)이 설치 되어 있어야 합니다. [Visual c + + 2013 여기에 다운로드](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- 비즈니스용 Skype 서버 2015를 성공적으로 배포 해야 합니다.
    
## <a name="configuration-requirements"></a>구성 요구 사항
<a name="ConfigReqs"> </a>

스트레스 및 성능 도구를 성공적으로 실행 하기 위해서는 다음과 같은 추가 구성이 필요 합니다.
  
- 도메인 또는 로컬 관리자 그룹의 구성원으로 서버에 로그인 해야 합니다.
    
- 사용자 계정이 상주할 모든 프런트 엔드 서버 또는 Standard Edition 서버에 비즈니스용 Skype 서버 2015 사용자 만들기 도구 (UserProvisioningTool)를 설치할 수 없습니다.
    
- 사용자 만들기 도구가 여러 번 실행 되는 경우 Microsoft 통합 통신을 사용 하도록 설정 된 각 사용자에 게 고유한 전화 번호가 있어야 합니다.
    
- 페이지 파일 크기는 시스템에서 관리 되거나 컴퓨터 시스템의 RAM 용량의 1.5 배 이상 이어야 합니다.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 설치
<a name="Installing"> </a>

설치 하는 것은 더 간단 합니다. 사용자 트래픽을 시뮬레이트하는 데 사용할 각 클라이언트 컴퓨터에서 Windows Installer 파일인 **CapacityPlanningTool**를 실행 하 고 사용자와 연락처를 만들 각 풀의 프런트 엔드 서버에서을 실행 해야 합니다.
  
다른 문서에 언급 된 예제 스크립트와 함께 .msi를 다운로드 하려면 다운로드 센터 링크: 비즈니스용 [Skype 서버 2015, 스트레스 및 성능 도구](https://www.microsoft.com/download/details.aspx?id=50367)를 참조 하세요.
  

