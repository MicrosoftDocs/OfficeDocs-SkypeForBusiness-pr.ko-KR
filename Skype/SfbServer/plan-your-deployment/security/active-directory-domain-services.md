---
title: Active Directory Domain Services for 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 도메인 서비스는 Windows Server 2003, Windows Server 2008, Windows Server 2012 R2 네트워크의 디렉터리 Windows Server 2012 기능입니다. Active Directory 도메인 서비스는 또한 보안 인프라가 구축되는 비즈니스용 Skype 서버 역할을 합니다. 이 섹션에서는 Active Directory 도메인 서비스를 비즈니스용 Skype 서버, 웹 회의, 미디어 및 음성에 대해 신뢰할 수 있는 환경을 만드는 방법을 설명합니다. Active Directory 도메인 서비스에 대한 환경을 준비하는 데 대한 자세한 내용은 배포 설명서에서 Install 비즈니스용 Skype 서버 참조하십시오. Windows Server 네트워크에서 Active Directory 도메인 서비스의 역할에 대한 자세한 내용은 사용 중인 운영 체제의 버전에 대한 설명서를 참조하십시오.
ms.openlocfilehash: 4af4e4b4dd7a64dd133d36a55ca1c334a12fe97e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604657"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Active Directory Domain Services for 비즈니스용 Skype 서버
 
Active Directory 도메인 서비스는 Windows Server 2003, Windows Server 2008, Windows Server 2012 R2 네트워크의 디렉터리 Windows Server 2012 기능입니다. Active Directory 도메인 서비스는 또한 보안 인프라가 구축되는 비즈니스용 Skype 서버 역할을 합니다. 이 섹션에서는 Active Directory 도메인 서비스를 비즈니스용 Skype 서버, 웹 회의, 미디어 및 음성에 대해 신뢰할 수 있는 환경을 만드는 방법을 설명합니다. Active Directory 도메인 서비스에 대한 환경을 준비하는 데 대한 자세한 내용은 배포 설명서에서 [Install 비즈니스용 Skype 서버](../../deploy/install/install.md) 참조하십시오. Windows Server 네트워크에서 Active Directory 도메인 서비스의 역할에 대한 자세한 내용은 사용 중인 운영 체제의 버전에 대한 설명서를 참조하십시오.
  
비즈니스용 Skype 서버 Active Directory 도메인 서비스를 사용하여 다음을 저장합니다.
  
- 포리스트에서 실행되는 모든 비즈니스용 Skype 서버 전역 설정
    
- 포리스트에서 실행되는 모든 서버의 역할을 비즈니스용 Skype 서버 정보입니다.
    
- 일부 사용자 설정
    
## <a name="active-directory-infrastructure"></a>Active Directory 인프라

Active Directory의 인프라 요구 사항은 다음과 같습니다.
  
- 도메인 컨트롤러에 대한 운영 체제 요구 사항
    
- 도메인 및 포리스트 기능 수준 요구 사항
    
- 글로벌 카탈로그 도메인 요구 사항
    
자세한 내용은 [2015의](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 환경 요구 사항 또는 비즈니스용 Skype 서버 [2019에 대한 서버](../../../SfBServer2019/plan/system-requirements.md)요구 사항을 비즈니스용 Skype 서버 참조하세요.
  
## <a name="universal-groups"></a>유니버설 그룹

포리스트를 준비하는 비즈니스용 Skype 서버 전역 설정 및 서비스를 액세스하고 관리할 수 있는 권한이 있는 다양한 유니버설 그룹을 Active Directory 도메인 서비스 내에 만듭니다. 이러한 유니버설 그룹은 다음과 같습니다.
  
- **관리 그룹**. 이러한 그룹은 네트워크의 기본 관리자 역할을 비즈니스용 Skype 서버 정의합니다. 포리스트 준비 중에 이러한 관리자 그룹이 비즈니스용 Skype 서버 그룹에 추가됩니다.
    
- **서비스 그룹**. 이러한 그룹은 그룹에서 제공하는 다양한 서비스에 액세스하는 데 필요한 서비스 비즈니스용 Skype 서버.
    
- **인프라 그룹**. 이러한 그룹은 네트워크 인프라의 특정 영역에 비즈니스용 Skype 서버 권한을 제공합니다. 이 그룹은 관리 그룹의 구성 요소로 작동하므로 이 그룹을 수정하거나 이 그룹에 사용자를 직접 추가해서는 안 됩니다. 포리스트를 준비하는 동안 특정 서비스 및 관리 그룹이 적절한 인프라 그룹에 추가됩니다.
    
비즈니스용 Skype 서버 AD를 준비할 때 만들어진 특정 유니버설 그룹과 인프라 그룹에 추가되는 서비스 및 관리 그룹에 [](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 대한 자세한 내용은 배포 설명서의 비즈니스용 Skype 서버 포리스트 준비에 의해 변경된 사항을 참조하십시오.
  
> [!NOTE]
> 비즈니스용 Skype 서버 도메인 컨트롤러의 Windows Server 2012 및 Windows Server 2003 운영 체제를 지원합니다. 유니버설 그룹의 구성원은 도메인 트리 또는 포리스트에 있는 도메인의 다른 그룹 및 계정을 포함할 수 있고 도메인 트리 또는 포리스트에 있는 도메인의 사용 권한이 할당될 수 있습니다. 유니버설 그룹 지원은 관리자 위임과 결합되어 사용자 지정 배포를 비즈니스용 Skype 서버 간소화합니다. 예를 들어 한 도메인을 다른 도메인에 추가하지 않아도 관리자가 둘 다 관리할 수 있습니다. 
  
## <a name="role-based-access-control"></a>역할 기반 액세스 제어

포리스트 준비에서는 유니버설 서비스 및 관리 그룹을 만들고 서비스 및 관리 그룹을 적절한 유니버설 그룹에 추가하는 것 외에도 RBAC(액세스 제어) Role-Based 만듭니다. 포리스트 준비로 만든 특정 RBAC 그룹에 [](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 대한 자세한 내용은 배포 설명서의 비즈니스용 Skype 서버 포리스트 준비로 변경을 참조하십시오. RBAC 그룹에 대한 자세한 내용은 에서 [RBAC(역할 기반 액세스 제어)를 비즈니스용 Skype 서버.](role-based-access-control-rbac.md)
  
## <a name="access-control-entries-aces-and-inheritance"></a>ACE(액세스 제어 항목) 및 상속성

포리스트 준비 중에는 개인 및 공용 ACE를 모두 만들어서 만들어진 유니버설 그룹에 ACE를 추가합니다. 전역 설정 컨테이너에서 사용하는 전역 설정 컨테이너에 특정 개인 AES를 비즈니스용 Skype 서버. 이 컨테이너는 전역 비즈니스용 Skype 서버 저장하는 위치에 따라 구성 컨테이너 또는 루트 도메인의 시스템 컨테이너에 있습니다.
  
도메인 준비 단계에서는 호스트에 권한을 부여하고 도메인 내의 사용자를 관리하는 유니버설 그룹에 필요한 ACE(액세스 제어 항목)를 추가합니다. 도메인 준비는 도메인 루트와 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 ACE를 만듭니다.
  
포리스트 준비 및 도메인 준비를 통해 만들어 추가된 [](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 공용 AES에 대한 자세한 내용은 [](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) 배포 설명서의 비즈니스용 Skype 서버 도메인 준비로 만든 변경 내용 및 비즈니스용 Skype 서버 참조하세요.
  
조직에서는 보안 위험을 줄이기 위해 AD DS(Active Directory 도메인 서비스)를 잠그는 경우가 자주 있습니다. 그러나 잠긴 Active Directory 환경에서는 액세스 권한이 제한될 비즈니스용 Skype 서버 있습니다. 여기에는 컨테이너 및 OU에서 ACE 제거, User, Contact, InetOrgPerson 또는 Computer 개체에 대한 권한 상속 비활성화가 포함됩니다. 잠겨 있는 Active Directory 환경에서는 권한이 필요한 컨테이너 및 OU에서 권한을 수동으로 설정해야 합니다.
  
## <a name="server-information"></a>서버 정보

정품 인증 비즈니스용 Skype 서버 Active Directory 도메인 서비스의 다음 세 위치에 서버 정보를 게시합니다.
  
- 설치되는 실제 컴퓨터에 해당하는 각 Active Directory 컴퓨터 개체의 SCP(서비스 연결 지점)비즈니스용 Skype 서버 지점입니다.
    
- **msRTCSIP-Pools** 클래스의 컨테이너에 만든 서버 개체
    
- 토폴로지 작성기에서 지정한 신뢰할 수 있는 서버.
    
## <a name="service-connection-points"></a>서비스 연결 지점

Active Directory 도메인 서비스의 각 비즈니스용 Skype 서버 개체에는 RTC Services라는 SCP가 있으며, 이 SCP에는 각 컴퓨터를 식별하고 해당 컴퓨터에서 제공하는 서비스를 지정하는 여러 특성이 포함됩니다. 보다 중요한 SCP 특성 중에는 *serviceDNSName,* *serviceDNSNameType,* *serviceClassname* 및 *serviceBindingInformation이 있습니다.* 타사 자산 관리 응용 프로그램은 이러한 특성 및 기타 SCP 특성에 대해 쿼리하여 배포 전체에서 서버 정보를 검색할 수 있습니다.
  
## <a name="active-directory-server-objects"></a>Active Directory 서버 개체

각 비즈니스용 Skype 서버 서버 역할에는 해당 역할에서 제공하는 서비스를 정의하는 해당 Active Directory 개체가 있습니다. 또한 Standard Edition 서버가 활성화되거나 Enterprise Edition 풀을 만들 때 비즈니스용 Skype 서버 **msRTCSIP-Pools** 컨테이너에 새 **msRTCSIP-Pool** 개체를 만듭니다. **msRTCSIP-Pool** 클래스는 풀의 FQDN(정규화된 도메인 이름) 및 풀의 프런트 엔드와 백 엔드 구성 요소 간 연결을 지정합니다. Standard Edition 서버는 프런트 엔드 및 백 엔드가 같은 컴퓨터에 배치되는 논리적 풀로 간주됩니다.
  
## <a name="trusted-servers"></a>트러스트된 서버

이 비즈니스용 Skype 서버 신뢰할 수 있는 서버는 토폴로지 작성기 실행 및 토폴로지 게시 시 지정된 서버입니다. 모든 서버 정보를 포함하여 게시된 토폴로지는 중앙 관리 저장소에 저장됩니다. 중앙 관리 저장소에 정의된 서버만 트러스트됩니다. 이 비즈니스용 Skype 서버 신뢰할 수 있는 서버는 다음 기준을 충족하는 서버입니다.
  
- 서버의 FQDN은 중앙 관리 저장소에 저장된 토폴로지에 발생합니다.
    
- 서버는 트러스트된 CA에서 적합한 인증서를 제공합니다. 자세한 내용은 [2015의](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 환경 요구 사항 또는 비즈니스용 Skype 서버 [2019에](../../../SfBServer2019/plan/system-requirements.md)대한 시스템 요구 사항을 비즈니스용 Skype 서버 참조하세요.
    
이러한 기준 중 하나라도 맞지 않으면 서버가 트러스트되지 않고 서버와의 연결이 거부됩니다. 이 이중 요구 사항은 가능하지 않은 경우 Rogue 서버가 유효한 서버의 FQDN을 인계하려고 시도하는 공격을 방지합니다.
  
또한 Microsoft Office Communications Server 2007 R2 및 Microsoft Office Communications Server 2007 배포에서 비즈니스용 Skype 서버 서버와 통신할 수 있도록 설정하기 위해 비즈니스용 Skype 서버 이전 릴리스에 대한 신뢰할 수 있는 서버 목록을 보관하기 위한 포리스트 준비 중에 컨테이너를 만듭니다. 다음 표에서는 이전 배포와의 호환성을 위해 만드는 컨테이너에 대해 설명합니다.
  
**트러스트된 서버 목록 및 이전 릴리스와의 호환성을 위한 해당 Active Directory 컨테이너**

|**트러스트된 서버 목록**|**Active Directory 컨테이너**|
|:-----|:-----|
|Standard Edition 서버 및 엔터프라이즈 풀 프런트 엔드 서버  <br/> |RTC 서비스/전역 설정  <br/> |
|회의 서버  <br/> |RTC 서비스/트러스트된 MCU  <br/> |
|웹 구성 요소 서버  <br/> |RTC 서비스/TrustedWebComponentsServers  <br/> |
|중재 서버 및 Communicator Web Access 서버, 응용 프로그램 서버, QoE 등록자, A/V 회의 서비스(타사 SIP 서버도 포함)  <br/> |RTC 서비스/트러스트된 서비스  <br/> |
|프록시 서버  <br/> |비즈니스용 Skype 서버 프록시 서버에 대한 호환성을 지원하지 않습니다.  <br/> |
   

## <a name="see-also"></a>참고 항목

[사용자에 대해 Active Directory 비즈니스용 Skype 서버](../../deploy/install/prepare-active-directory.md)
