---
title: 비즈니스용 Skype 서버용 Active Directory 도메인 서비스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 도메인 서비스는 Windows Server 2003, Windows Server 2008, Windows Server 2012 및 Windows Server 2012 R2 네트워크에 대 한 디렉터리 서비스로 작동 합니다. Active Directory 도메인 서비스는 또한 비즈니스용 Skype 서버 보안 인프라의 기반이 되는 토대 역할을 합니다. 이 섹션에서는 비즈니스용 Skype 서버에서 Active Directory 도메인 서비스를 사용 하 여 IM, 웹 회의, 미디어, 음성에 대 한 신뢰할 수 있는 환경을 만드는 방법을 설명 합니다. Active Directory 도메인 서비스의 환경을 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에 비즈니스용 Skype 서버 설치를 참조 하세요. Windows Server 네트워크용 Active Directory 도메인 서비스의 역할에 대 한 자세한 내용은 사용 중인 운영 체제 버전에 대 한 설명서를 참조 하세요.
ms.openlocfilehash: ec3a09e2203b6f862d87403818b43ab6daae33ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815716"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 Active Directory 도메인 서비스
 
Active Directory 도메인 서비스는 Windows Server 2003, Windows Server 2008, Windows Server 2012 및 Windows Server 2012 R2 네트워크에 대 한 디렉터리 서비스로 작동 합니다. Active Directory 도메인 서비스는 또한 비즈니스용 Skype 서버 보안 인프라의 기반이 되는 토대 역할을 합니다. 이 섹션에서는 비즈니스용 Skype 서버에서 Active Directory 도메인 서비스를 사용 하 여 IM, 웹 회의, 미디어, 음성에 대 한 신뢰할 수 있는 환경을 만드는 방법을 설명 합니다. Active Directory 도메인 서비스의 환경을 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에 [비즈니스용 Skype 서버 설치](../../deploy/install/install.md) 를 참조 하세요. Windows Server 네트워크용 Active Directory 도메인 서비스의 역할에 대 한 자세한 내용은 사용 중인 운영 체제 버전에 대 한 설명서를 참조 하세요.
  
비즈니스용 Skype Server는 Active Directory 도메인 서비스를 사용 하 여 다음을 저장 합니다.
  
- 포리스트에서 비즈니스용 Skype 서버를 실행 하는 모든 서버에 게 필요한 전역 설정입니다.
    
- 포리스트에서 비즈니스용 Skype 서버를 실행 하는 모든 서버의 역할을 식별 하는 서비스 정보입니다.
    
- 일부 사용자 설정
    
## <a name="active-directory-infrastructure"></a>Active Directory 인프라

Active Directory의 인프라 요구 사항에는 다음이 포함 됩니다.
  
- 도메인 컨트롤러에 대 한 운영 체제 요구 사항
    
- 도메인 및 포리스트 기능 수준 요구 사항
    
- 글로벌 카탈로그 도메인 요구 사항
    
자세한 내용은 비즈니스용 [Skype server 2015의 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 비즈니스용 [skype server 2019에 대 한 서버 요구](../../../SfBServer2019/plan/system-requirements.md)사항을 참조 하세요.
  
## <a name="universal-groups"></a>유니버설 그룹

포리스트를 준비 하는 동안 비즈니스용 Skype Server는 Active Directory 도메인 서비스 내에서 전역 설정 및 서비스에 액세스 하 고 관리 하는 데 필요한 권한이 있는 다양 한 유니버설 그룹을 만듭니다. 이러한 유니버설 그룹에는 다음이 포함 됩니다.
  
- **관리 그룹**. 이 그룹은 비즈니스용 Skype Server 네트워크의 기본 관리자 역할을 정의 합니다. 포리스트를 준비 하는 동안 이러한 관리자 그룹은 비즈니스용 Skype 서버 인프라 그룹에 추가 됩니다.
    
- **서비스 그룹**. 이러한 그룹은 비즈니스용 Skype 서버에서 제공 하는 다양 한 서비스에 액세스 하는 데 필요한 서비스 계정입니다.
    
- **인프라 그룹** 이러한 그룹은 비즈니스용 Skype 서버 인프라의 특정 영역에 액세스할 수 있는 권한을 제공 합니다. 관리 그룹의 구성 요소로 작동 하므로이를 수정 하거나 직접 사용자를 추가 해서는 안 됩니다. 포리스트를 준비 하는 동안 특정 서비스 및 관리 그룹이 해당 인프라 그룹에 추가 됩니다.
    
비즈니스용 Skype Server에 대 한 광고를 준비할 때 생성 되는 특정 유니버설 그룹 및 인프라 그룹에 추가 되는 서비스 및 관리 그룹에 대 한 자세한 내용은 배포 설명서의 [비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 내용을](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 참조 하세요.
  
> [!NOTE]
> 비즈니스용 Skype 서버는 Windows Server 2012의 유니버설 그룹과 도메인 컨트롤러용 Windows Server 2003 운영 체제를 지원 합니다. 유니버설 그룹의 구성원은 도메인 트리나 포리스트에 있는 모든 도메인의 다른 그룹 및 계정을 포함할 수 있으며, 도메인 트리나 포리스트의 모든 도메인에서 사용 권한을 할당할 수 있습니다. 관리자 위임과 통합 된 유니버설 그룹 지원으로 인해 비즈니스용 Skype 서버 배포 관리가 간단해 집니다. 예를 들어 관리자가 둘 다 관리할 수 있도록 한 도메인을 다른 도메인에 추가할 필요는 없습니다. 
  
## <a name="role-based-access-control"></a>역할 기반 액세스 제어

유니버설 서비스 및 관리 그룹을 만들고 서비스 및 관리 그룹을 적절 한 유니버설 그룹에 추가 하는 것 외에도 포리스트 준비는 RBAC (역할 기반 액세스 제어) 그룹을 만듭니다. 포리스트 준비로 만든 특정 RBAC 그룹에 대 한 자세한 내용은 배포 설명서의 [비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 내용을](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 참조 하세요. RBAC 그룹에 대 한 자세한 내용은 [비즈니스용 Skype 서버용 RBAC (역할 기반 액세스 제어](role-based-access-control-rbac.md))를 참조 하세요.
  
## <a name="access-control-entries-aces-and-inheritance"></a>Ace (액세스 제어 항목) 및 상속

포리스트 준비는 개인 Ace를 만들고 자신이 만든 유니버설 그룹에 Ace를 추가 합니다. 비즈니스용 Skype 서버에서 사용 하는 전역 설정 컨테이너에 특정 개인 Ace를 만듭니다. 이 컨테이너는 비즈니스용 Skype Server 에서만 사용 되며, 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너 또는 시스템 컨테이너에 위치 합니다.
  
도메인 준비 단계에서는 도메인 내에서 사용자를 호스트 하 고 관리할 수 있는 권한을 부여 하는 유니버설 그룹에 필요한 Ace (액세스 제어 항목)를 추가 합니다. 도메인 준비는 도메인 루트 및 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에 Ace를 만듭니다.
  
포리스트 준비 및 도메인 준비에 의해 만들어지고 추가 되는 공개 Ace에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 포리스트 준비](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) 에서 변경한 내용 및 배포 설명서의 비즈니스용 [skype 서버에서 도메인 준비](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) 에의 한 변경 사항에 대해 알아보세요.
  
조직에서 보안 위험을 줄일 수 있도록 AD DS (Active Directory 도메인 서비스)를 잠그는 경우가 많습니다. 그러나 잠겨 있는 Active Directory 환경은 비즈니스용 Skype 서버에 필요한 권한을 제한할 수 있습니다. 여기에는 컨테이너 및 Ou에서 Ace를 제거 하 고 사용자, 연락처, InetOrgPerson 또는 컴퓨터 개체에 대 한 사용 권한 상속을 사용 하지 않도록 설정할 수 있습니다. Active Directory 환경 잠겨 있는 경우에는 컨테이너 및이를 필요로 하는 Ou에 대 한 사용 권한을 수동으로 설정 해야 합니다.
  
## <a name="server-information"></a>서버 정보

정품 인증 하는 동안 비즈니스용 Skype Server는 Active Directory 도메인 서비스의 다음 세 위치에 서버 정보를 게시 합니다.
  
- 비즈니스용 Skype 서버가 설치 되어 있는 물리적 컴퓨터에 해당 하는 각 Active Directory 컴퓨터 개체의 SCP (서비스 연결 지점)입니다.
    
- **MsRTCSIP** 클래스의 컨테이너에서 만들어진 서버 개체
    
- 토폴로지 작성기에 지정 된 신뢰할 수 있는 서버
    
## <a name="service-connection-points"></a>서비스 연결 지점

Active Directory 도메인 서비스의 각 비즈니스용 Skype Server 개체에는 RTC Services 라는 SCP가 있으며, 여기에는 각 컴퓨터를 식별 하 고 제공 하는 서비스를 지정 하는 여러 특성이 포함 됩니다. 중요 한 SCP 특성 중에는 *serviceDNSName* , *serviceDNSNameType* , *serviceClassname* 및 *serviceBindingInformation* 가 있습니다. 타사 자산 관리 응용 프로그램은 이러한 특성과 다른 SCP 특성에 대해 쿼리 하 여 배포에서 서버 정보를 검색할 수 있습니다.
  
## <a name="active-directory-server-objects"></a>Active Directory 서버 개체

각 비즈니스용 Skype Server 서버 역할에는 해당 특성이 해당 역할에서 제공 하는 서비스를 정의 하는 해당 Active Directory 개체가 있습니다. 또한 Standard Edition 서버를 정품 인증 하거나 Enterprise Edition 풀을 만들 때 비즈니스용 Skype 서버에서 **MsRTCSIP 풀** 컨테이너에 새 **msRTCSIP 풀** 개체를 만듭니다. **MsRTCSIP** 클래스는 풀의 FQDN (정규화 된 도메인 이름)을 풀의 프런트 엔드 및 백 엔드 구성 요소 간 연결과 함께 지정 합니다. (스탠더드 버전 서버는 한 컴퓨터에서 앞 및 뒤 끝을 collocated 논리적 풀로 간주 됩니다.)
  
## <a name="trusted-servers"></a>신뢰할 수 있는 서버

비즈니스용 Skype 서버에서 신뢰 하는 서버는 토폴로지 작성기를 실행 하 고 토폴로지를 게시할 때 지정 합니다. 모든 서버 정보를 포함 하 여 게시 된 토폴로지가 중앙 관리 저장소에 저장 됩니다. 중앙 관리 저장소에 정의 된 서버만 신뢰할 수 있습니다. 비즈니스용 Skype 서버에서 신뢰할 수 있는 서버는 다음 조건을 충족 하는 것입니다.
  
- 중앙 관리 저장소에 저장 된 토폴로지에서 서버의 FQDN이 발생 합니다.
    
- 서버는 신뢰할 수 있는 CA에서 유효한 인증서를 제공 합니다. 자세한 내용은 비즈니스용 Skype Server 2015 또는 비즈니스용 [Skype server 2019의 시스템 요구](../../../SfBServer2019/plan/system-requirements.md)사항에 [대 한 환경 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 참조 하세요.
    
이러한 조건 중 하나라도 없으면 서버를 신뢰할 수 없고 연결이 거부 됩니다. 이 double 요구 사항은 rogue 서버에서 유효한 서버의 FQDN을 사용 하려고 시도 하는 공격 가능성을 방지 합니다.
  
또한 Microsoft Office Communications Server 2007 R2 및 Microsoft Office Communications Server 2007 배포를 사용 하 여 비즈니스용 Skype 서버 서버와 통신 하기 위해 비즈니스용 Skype Server는 포리스트를 준비 하는 동안 컨테이너를 만듭니다. 이전 릴리스에 대해 신뢰할 수 있는 서버 목록을 보관 합니다. 다음 표에서는 이전 배포와의 호환성을 사용 하도록 만들어진 컨테이너에 대해 설명 합니다.
  
**이전 릴리스와의 호환성을 위해 신뢰할 수 있는 서버 목록과 해당 Active Directory 컨테이너**

|**신뢰 된 서버 목록**|**Active Directory 컨테이너**|
|:-----|:-----|
|스탠더드 버전 서버 및 엔터프라이즈 풀 프런트 엔드 서버  <br/> |RTC 서비스/전역 설정  <br/> |
|회의 서버  <br/> |RTC 서비스/신뢰할 수 있는 MCUs  <br/> |
|웹 구성 요소 서버  <br/> |RTC 서비스/TrustedWebComponentsServers  <br/> |
|중재 서버 및 Communicator Web Access 서버, 응용 프로그램 서버, 체감 품질를 사용 하는 등록 기관, A/V 회의 서비스 (타사 SIP 서버 이기도)  <br/> |RTC 서비스/신뢰할 수 있는 서비스  <br/> |
|프록시 서버  <br/> |비즈니스용 Skype 서버는 프록시 서버에 대 한 이전 버전과의 호환성을 지원 하지 않습니다.  <br/> |
   

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에 대 한 Active Directory 준비](../../deploy/install/prepare-active-directory.md)
