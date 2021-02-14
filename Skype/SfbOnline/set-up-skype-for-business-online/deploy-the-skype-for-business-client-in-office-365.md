---
title: Microsoft 365 aor Office 365에서 비즈니스용 Skype 클라이언트 배포
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '중소기업 및 대규모 조직에서 비즈니스용 Skype를 계획 및 배포하고 사용자가 사용할 수 있도록 하는 방법을 배워보는 방법을 배워야 합니다. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777243"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365에서 비즈니스용 Skype 클라이언트 배포

이 문서에서는 관리자인 사용자가 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 조직의 사용자에게 비즈니스용 Skype 앱을 배포하는 방법에 대한 옵션을 설명하고 있습니다.
  
사용자에게 비즈니스용 Skype를 배포하기 전에 비즈니스용 Skype Online 설정 문서의 1-3단계를 [완료해야 합니다.](set-up-skype-for-business-online.md) 이렇게 하면 비즈니스용 Skype가 도메인으로 설정되어 모든 사용자가 라이선스를 가지며 조직에 맞게 비즈니스용 [Skype Online에서](configure-presence-in-skype-for-business-online.md) IM 및 현재 상태 구성을 구성하게 됩니다.
  
> [!NOTE]
> 비즈니스용 Skype 앱을 설치하려면 PC 또는 장치에서 로컬 관리자로 설정해야 합니다. 또는 PC 또는 장치에 앱을 설치할 수 있는 로컬 그룹에 참여해야 합니다. 사용자가 자신의 장치에 소프트웨어를 설치할 수 없는 경우 비즈니스용 Skype 앱을 설치해야 합니다. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>대부분의 중소기업

 **단계별 설치 지침:** 중소기업이 있는 경우 사용자에게 PC에 비즈니스용 Skype 앱을 설치하도록 요청하는 것이 좋습니다. 다음 지침을 [안내하세요. 비즈니스용 Skype를 설치하세요.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Mac을 사용하는 경우 Office [365용 Lync for Mac 2011을](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)설정해야 합니다. 비즈니스용 Skype 앱은 나머지 Office 앱과 별도로 설치됩니다.
  
 엔터프라이즈 고객을 위한 **Microsoft 365 앱:** 비즈니스에서 E3 요금제와 같은 엔터프라이즈용 Microsoft 365 앱을 포함하는 Office 365 요금제를 사용하는 경우 사용자가 Word, Excel, PowerPoint 등을 다운로드하고 설치하는 동시에 비즈니스용 Skype 앱이 설치됩니다. 또한 Office를 모두 제거하지 않으면 비즈니스용 Skype를 제거하지 못합니다.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>사용자가 비즈니스용 Skype를 사용할 수 있도록 할지 여부를 선택하세요.

관리자는 사용자가 [비즈니스용](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) Skype 앱을 사용할 수 있도록 할지 여부를 선택할 수 있습니다.
  
- **회사의** 모든 사용자가 소프트웨어를 받을지 여부를 제어하려면 Microsoft 365 관리 센터에 로그인하고 내 소프트웨어 설치로 이동한 다음 사용자가 사용할 수 있는 소프트웨어를 선택합니다. 
    
    ![회사 내 사람들이 사용할 수 있도록 하려는 소프트웨어를 선택하십시오.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- 회사의 특정 사용자가 소프트웨어를 받을지 여부를 제어하려면 **Microsoft** 365 관리 센터에 로그인하고 사용자 활성 사용자로 이동하여 소프트웨어에 대한 액세스 권한을 부여할 사용자를 선택한 다음 제품 라이선스 옆에 있는 편집을 클릭하고 라이선스를 설정하거나   >  해제합니다.  
    
    ![사용자가 액세스할 소프트웨어를 선택하십시오.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 조직의 사용자에게 할당된 계획을 확인하려면 사용자 활성 사용자에 대해 Microsoft 365 관리 센터에 >  >  **합니다.** 목록에서 사람을 선택한 다음 **제품 라이선스를 살펴 봐야 합니다.** 클래식 관리 센터를 사용하는 경우 할당된 **라이선스를 살펴 봐야 합니다.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>사용자에게 비즈니스용 Skype 수동 배포
<a name="bkmk_manual_1"> </a>

사용자가 인터넷이 아닌 네트워크의 위치에서 비즈니스용 Skype 앱을 설치하도록 하려는 경우 설치 파일을 다운로드할 수 있습니다. 이렇게하려면 Microsoft 365 관리 센터의 사용자 소프트웨어 수동 배포 섹션으로 이동하세요.  그런 다음 **설치를** 선택하고 설치 .exe 파일을 네트워크 위치에 저장할 수 있습니다.
  
또 다른 옵션은 사용자를 위한 비즈니스용 Skype Basic 앱을 다운로드하는 것입니다. Microsoft 비즈니스용 [Skype Basic(32 또는 64비트)을 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=49440)
  
전체 및 기본 비즈니스용 Skype 앱의 경우 설치 파일을 다운로드한 후 사용자가 컴퓨터에 앱을 설치하기 위해 설치 프로그램을 실행할 수 있도록 사용자에게 네트워크 경로를 수동으로 보내야 합니다(예: 전자 메일).
  
이러한 다운로드를 사용하여 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 사용자에게 비즈니스용 Skype 앱을 배포할 수도 있습니다.
  
## <a name="for-larger-and-enterprise-organizations"></a>대규모 및 엔터프라이즈 조직의 경우

> [!NOTE]
> 이 섹션은 Office 365 요금제에서 사용할 수 있는 비즈니스용 Skype 앱에만 적용됩니다. 조직에서 Windows Installer 기반(MSI)인 비즈니스용 Skype 앱의 볼륨 라이선스 버전을 사용하는 경우 비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정을 [참조하세요.](https://technet.microsoft.com/library/jj204934.aspx)
  
많은 기업 또는 대규모 조직에서는 사용자가 자신의 컴퓨터에 소프트웨어를 설치할 수 없습니다. 대신 IT 부서에서 필요한 소프트웨어를 사용자의 컴퓨터에 배포합니다. IT 부서는 조직에서 사용되는 인터넷 또는 네트워크 대역폭의 양을 제어하여 인터넷을 통해 또는 회사 네트워크를 가로지르는 대신 네트워크의 근처 위치에서 소프트웨어를 설치하려는 경우도 있습니다.
  
Office 365를 사용하면 설치된 위치를 제어하려는 경우 비즈니스용 Skype 앱을 배포할 수 있는 몇 가지 옵션이 있습니다. 이러한 옵션 중 일부는 다음과 같습니다.
  
- 사용자에게 비즈니스용 Skype 수동 배포에 설명된 바와 같이 Microsoft 365 관리 센터에서 로컬 네트워크에 비즈니스용 Skype 앱을 [다운로드합니다.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Office 배포 **[도구를](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 사용하여 엔터프라이즈용 Microsoft 365 앱 또는 비즈니스용 Skype 앱을 로컬 네트워크에 다운로드합니다. 그런 다음 Office 배포 도구를 사용하여 사용자에게 앱을 배포합니다. Office 배포 도구는 언어 및 버전(32비트 또는 64비트)과 같은 배포의 특정 측면을 제어하는 기능을 제공합니다.
    
- Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 엔터프라이즈용 Microsoft 365 앱 또는 비즈니스용 Skype 앱을 사용자에게 배포합니다. Office 배포 도구 또는 Microsoft [](https://go.microsoft.com/fwlink/p/?LinkID=626065) 365 관리 센터에서 다운로드한 소프트웨어와 함께 기존 도구 및 프로세스를 사용할 수 있습니다.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 배포 도구 사용에 대한 자세한 정보

Office 배포 도구 다운로드에 대한 자세한 내용 및 비즈니스용 Skype 앱 및 기타 Office 365 클라이언트 앱 설치에 대한 자세한 내용은 [Office 365에서](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)소프트웨어 다운로드 설정 관리를 참조하세요.
  
다음은 Office 배포 도구를 사용하여 앱을 배포하는 데 관련된 단계의 개요입니다.
  
1. **[Microsoft 다운로드 센터에서 최신 Office](https://www.microsoft.com/download/details.aspx?id=49117)** 배포 도구를 다운로드합니다.
    
2. 버전 configuration.xml(32비트 또는 64비트), 설치 언어 등 원하는 클라이언트 앱 설정이 있는 Office 배포 도구에서 사용할 configuration.xml 파일을 만들 수 있습니다.
    
3. Office 배포 도구 및 configuration.xml 파일을 사용하여 Office CDN(Content Delivery Network)에서 로컬 또는 내부 네트워크에 설치 파일을 다운로드합니다.
    
4. Office 배포 도구 및 configuration.xml 사용하여 비즈니스용 Skype 앱을 비롯한 Office 클라이언트 앱을 설치합니다.
    
Office 배포 도구 및 파일 configuration.xml 자세한 내용은 다음 문서를 참조하세요.
  
- [Office 배포 도구 개요](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml 설정](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager 사용에 대한 자세한 정보

Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 비즈니스용 Skype 앱을 배포할 수 있습니다. Microsoft 365 관리 센터에서 다운로드한 소프트웨어 또는 Office 배포 도구를 사용하여 이러한 도구 및 프로세스를 사용할 수 있습니다.
  
구성 관리자를 사용하여 소프트웨어를 배포하는 데 대한 자세한 내용은 다음 문서를 참조하세요.
  
- [Configuration Manager에서 애플리케이션 만들기](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Configuration Manager를 통해 애플리케이션 배포](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
엔터프라이즈용 Microsoft 365 앱 배포의 일부로 비즈니스용 Skype 앱을 배포하는 경우 Configuration Manager를 사용하여 [엔터프라이즈용 Microsoft 365 앱 관리를 참조하세요.](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>비즈니스용 Skype 앱 업데이트 계획

비즈니스용 Skype 앱을 배포할 때 비즈니스용 Skype를 설치한 후 업데이트를 받을 방법을 고려해야 합니다. 이러한 업데이트에는 안정성 또는 성능 향상을 제공하는 업데이트와 같은 새로운 기능, 보안 업데이트 또는 비보안 업데이트가 포함됩니다. 고려해야 할 두 가지 주요 사항:
  
- 어디에서 업데이트를 받을 수 있습니다.
    
- 기능 업데이트를 얼마나 자주 하려는가
    
업데이트의 위치와 기능 업데이트를 받을 수 있는 위치를 제어할 수 있는 반면, 어떤 특정 보안 업데이트 또는 비보안 업데이트를 받을지 선택할 수 없습니다.
  
 **업데이트를 받을 위치**
  
기본적으로 비즈니스용 Skype 앱이 설치되면 Microsoft에서 사용할 수 있을 때 업데이트가 인터넷에서 자동으로 다운로드됩니다. 업데이트가 발생하는 경우 또는 업데이트가 설치된 위치를 더 잘 제어하려면 Office 배포 도구 또는 그룹 정책을 사용하여 구성할 수 있습니다.
  
예를 들어 많은 조직에서는 조직 전체에 배포하기 전에 사용자 그룹으로 업데이트를 테스트하려는 경우를 예로 들 수 있습니다. 이 작업을 수행하려면 Office 배포 도구 또는 그룹 정책을 사용하여 인터넷에서 자동으로 업데이트되는 대신 네트워크의 특정 위치에서 업데이트를 하도록 비즈니스용 Skype 앱을 구성할 수 있습니다. 그런 다음 Office 배포 도구를 사용하여 로컬 네트워크에 매월 업데이트를 다운로드할 수 있습니다.
  
Office 365 소프트웨어에 대한 업데이트 작동 방식에 대한 자세한 내용은 다음 문서를 참조하세요.
  
- [엔터프라이즈용 Microsoft 365 앱에 대한 업데이트 프로세스 개요](https://technet.microsoft.com/library/dn761709.aspx)
    
- [엔터프라이즈용 Microsoft 365 앱에 대한 업데이트를 관리하는 방법 선택](https://technet.microsoft.com/library/dn761707.aspx)
    
- [엔터프라이즈용 Microsoft 365 앱에 대한 업데이트 설정 구성](https://technet.microsoft.com/library/dn761708.aspx)
    
  **기능 업데이트를 받을 수 있는 방법**
  
업데이트를 받을 수 있는 위치 외에도 비즈니스용 Skype 클라이언트의 새로운 기능을 얼마나 자주 받을지 제어할 수도 있습니다. 두 가지 선택은 다음과 같습니다.
  
- 새로운 기능이 있는 경우 매월 기능 업데이트를 받을 수 있습니다.
    
- 6개월마다 기능 업데이트 확인
    
일부 조직의 경우 매월이 아닌 1년에 두 번만 기능 업데이트를 받을 수 있도록 새로운 기능을 테스트할 시간을 원합니다.
  
Office 배포 도구 또는 그룹 정책을 사용하여 업데이트 채널을 구성하여 기능 업데이트를 받을 수 있는 자주 제어할 수 있습니다. 월별 채널은 기능 업데이트를 매월(약) 제공하는 반면 Semi-Annual 채널은 6개월마다 기능 업데이트를 제공합니다. 채널에 대한 자세한 내용은 [엔터프라이즈용 Microsoft 365 앱의](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)업데이트 채널 개요를 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)
  
[비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
