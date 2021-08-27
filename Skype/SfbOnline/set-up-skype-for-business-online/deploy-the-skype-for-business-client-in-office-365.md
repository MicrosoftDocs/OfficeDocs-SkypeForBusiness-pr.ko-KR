---
title: 비즈니스용 Skype aor Microsoft 365 클라이언트를 배포합니다Office 365
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '소규모, 중소 및 비즈니스용 Skype 조직에서 계획을 세우고 배포하고 사용자가 사용할 수 있도록 하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 3cfa319536c521ee4d0e3b297fd978071c93105d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589180"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>비즈니스용 Skype 클라이언트를 Microsoft 365 Office 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 문서에서는 관리자인 사용자가 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 조직의 사용자에게 비즈니스용 Skype 배포할 수 있는 방법에 대한 옵션을 설명합니다.
  
사용자에게 비즈니스용 Skype 전에 온라인 설정 문서에서 [1-3단계를 비즈니스용 Skype 합니다.](set-up-skype-for-business-online.md) 이렇게 하면 비즈니스용 Skype 설정하고 모든 사용자가 해당 라이선스를 가지며 조직에 대한 온라인에서 IM [및 비즈니스용 Skype 구성합니다.](configure-presence-in-skype-for-business-online.md)
  
> [!NOTE]
> 사용자가 비즈니스용 Skype 앱을 설치하려면 PC 또는 디바이스에 로컬 관리자로 설정해야 합니다. 또는 PC 또는 디바이스에 앱을 설치할 수 있는 로컬 그룹에 참여해야 합니다. 사용자가 해당 디바이스에 소프트웨어를 설치할 수 없는 경우 해당 디바이스에 대한 비즈니스용 Skype 설치해야 합니다. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>대부분의 중소기업의 경우

 **단계별 설치 지침:** 중소기업이 있는 경우 사용자에게 PC에 앱 설치를 비즈니스용 Skype 것이 좋습니다. 다음 지침을 지시합니다. [비즈니스용 Skype.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Mac을 사용하는 경우 Mac [2011용 Lync](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)설정 을 Office 365. 비즈니스용 Skype 앱은 나머지 앱과 별도로 Office 설치됩니다.
  
 **엔터프라이즈용 Microsoft 365 앱 고객:** 비즈니스 Office 365에서 비즈니스용 Skype e3 요금제와 엔터프라이즈용 Microsoft 365 앱 포함하는 엔터프라이즈용 Microsoft 365 앱 요금제를 사용하는 경우 사용자가 Word, Excel, PowerPoint 설치하는 동시에 PowerPoint. 즉, 모든 비즈니스용 Skype 제거하지 않는 한 Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>사용자가 사용할 수 있도록 비즈니스용 Skype 여부를 선택

관리자는 [](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) 사용자가 앱을 사용할 수 있도록 비즈니스용 Skype 선택할 수 있습니다.
  
- **회사의** 모든 사용자가 소프트웨어에 로그인하는지 여부를 제어하려면 Microsoft 365 관리 센터 설치로 이동한 다음 사용자가 사용할 수 있는 소프트웨어를 선택합니다.
    
    ![회사에 있는 사용자들이 사용할 수 있도록 할 소프트웨어를 선택하십시오.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **회사의** 특정 사용자가 소프트웨어에 로그인할지 여부를 제어하려면 Microsoft 365 관리 센터 사용자 활성 사용자로 이동하여 소프트웨어에 대한 액세스 권한을 부여할 사용자를 선택한 다음 제품 라이선스 옆에 있는 편집을 클릭한 다음 라이선스를 켜거나  >  해제합니다.  
    
    ![사용자가 액세스할 소프트웨어를 선택할 수 있습니다.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 조직의 사용자에게 할당된 계획을 확인해야 하는 경우 사용자 활성 사용자에게 Microsoft 365 관리 센터 >   >  **로그인합니다.** 목록에서 사람을 선택한 다음 제품 라이선스 **아래를 봐야 합니다.** 클래식 관리 센터를 사용하는 경우 할당된 라이선스 **를 살펴 봐야 합니다.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>사용자에게 비즈니스용 Skype 수동으로 배포
<a name="bkmk_manual_1"> </a>

사용자가 인터넷 대신 네트워크의 위치에서 비즈니스용 Skype 앱을 설치하려면 설치 파일을 다운로드할 수 있습니다. 이렇게하려면 사용자 소프트웨어의 수동으로 배포 섹션으로 Microsoft 365 관리 센터.  그런 다음 **설치를** 선택하고 네트워크 .exe 파일을 저장할 수 있습니다.
  
다른 옵션은 사용자에 대한 기본 비즈니스용 Skype 다운로드하는 것입니다. Microsoft 비즈니스용 Skype [기본(32비트 또는 64비트)을 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=49440)
  
전체 및 기본 비즈니스용 Skype 앱 모두에 대해 설정 파일을 다운로드한 후 사용자가 컴퓨터에 앱을 설치하도록 설치 프로그램을 실행할 수 있도록 사용자에 대한 네트워크 경로를 수동으로 보내야 합니다(예: 전자 메일).
  
또한 이러한 다운로드를 사용하여 기존 비즈니스용 Skype 배포 도구 및 프로세스를 사용하여 사용자에게 비즈니스용 Skype 앱을 배포할 수 있습니다.
  
## <a name="for-larger-and-enterprise-organizations"></a>대규모 및 엔터프라이즈 조직의 경우

> [!NOTE]
> 이 섹션은 비즈니스용 Skype 통해 사용할 수 있는 Office 365 앱에만 적용됩니다. 조직에서 MSI(설치 관리자 기반)인 비즈니스용 Skype 볼륨 라이선스 버전을 사용하는 경우 Windows 클라이언트 설치 Windows 사용자 지정을 [비즈니스용 Skype 서버.](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)
  
많은 기업 또는 대규모 조직에서 사용자는 컴퓨터에 소프트웨어를 설치할 수 없습니다. 대신 IT 부서는 사용자의 컴퓨터에 필요한 소프트웨어를 배포합니다. 또한 IT 부서는 조직에서 사용되는 인터넷 또는 네트워크 대역폭의 양을 제어하기를 원할 수 있으므로 인터넷을 가로질러 또는 회사 네트워크를 가로지르는 대신 네트워크의 가까운 위치에서 소프트웨어를 설치하려는 경우도 있습니다.
  
Office 365 설치 위치를 제어하려는 경우 비즈니스용 Skype 앱을 배포하기 위한 몇 가지 옵션이 있습니다. 이러한 옵션 중 일부는 다음과 같습니다.
  
- 사용자 비즈니스용 Skype 수동으로 배포에 설명된 Microsoft 365 관리 센터 로컬 네트워크에 비즈니스용 Skype [다운로드합니다.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- 배포 **[Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 도구를 사용하여 엔터프라이즈용 Microsoft 365 앱 또는 비즈니스용 Skype 앱을 로컬 네트워크에 다운로드합니다. 그런 다음, Office 배포 도구를 사용하여 사용자에게 앱을 배포합니다. Office 배포 도구를 사용하면 언어 및 버전(32비트 또는 64비트)과 같은 배포의 특정 측면을 제어할 수 있습니다.
    
- 기존 소프트웨어 배포 도구 및 프로세스(예: Microsoft Endpoint Configuration Manager)를 사용하여 사용자에게 엔터프라이즈용 Microsoft 365 앱 비즈니스용 Skype 배포합니다. 배포 도구 또는 Office 다운로드한 [](https://go.microsoft.com/fwlink/p/?LinkID=626065) 소프트웨어와 함께 기존 도구 및 프로세스를 사용할 Microsoft 365 관리 센터.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>배포 도구 사용에 대한 Office 자세한 정보

배포 도구 다운로드에 대한 Office 앱 및 기타 클라이언트 앱 설치에 대한 비즈니스용 Skype 자세한 내용은 Office 365 의 소프트웨어 다운로드 설정 [관리를 Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
다음은 앱을 배포하기 위해 배포 도구에 Office 단계에 대한 개요입니다.
  
1. Microsoft 다운로드 **[센터에서](https://www.microsoft.com/download/details.aspx?id=49117)** 최신 Office 배포 도구를 다운로드합니다.
    
2. 버전 configuration.xml(32비트 또는 64비트), 설치 언어 등 클라이언트 앱 설정이 있는 Office 배포 도구와 함께 사용할 파일 만들기
    
3. 배포 Office 및 configuration.xml 파일을 사용하여 설치 파일을 로컬 또는 Office Content Delivery Network 내부 네트워크에 CDN.
    
4. 배포 Office 및 configuration.xml 앱을 포함하여 Office 클라이언트 앱을 비즈니스용 Skype 사용합니다.
    
배포 도구 및 Office 및 configuration.xml 자세한 내용은 다음 문서를 참조하세요.
  
- [Office 배포 도구 개요](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml 설정](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>웹 사이트 사용에 대한 자세한 Microsoft Endpoint Configuration Manager

기존 소프트웨어 배포 도구 및 프로세스를 사용하여 Microsoft Endpoint Configuration Manager 앱을 배포할 비즈니스용 Skype 있습니다. 이러한 도구 및 프로세스를 배포 도구에서 다운로드하는 소프트웨어 또는 Microsoft 365 관리 센터 배포 도구와 함께 Office 수 있습니다.
  
Configuration Manager를 사용하여 소프트웨어 배포에 대한 자세한 내용은 다음 문서를 참조하세요.
  
- [Configuration Manager에서 애플리케이션 만들기](/configmgr/apps/deploy-use/create-applications)
    
- [Configuration Manager를 통해 애플리케이션 배포](/configmgr/apps/deploy-use/deploy-applications)
    
배포의 일환으로 비즈니스용 Skype 앱을 배포하는 엔터프라이즈용 Microsoft 365 앱 구성 관리자를 사용하여 엔터프라이즈용 Microsoft 365 앱 [참조하세요.](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>앱에 대한 업데이트 비즈니스용 Skype 계획

앱 배포의 일부로 비즈니스용 Skype 설치한 후 업데이트를 비즈니스용 Skype 고려해야 합니다. 이러한 업데이트에는 안정성 또는 성능 개선을 제공하는 업데이트와 같은 새로운 기능, 보안 업데이트 또는 비보안 업데이트가 포함됩니다. 고려해야 할 주요 두 가지는 다음과 같습니다.
  
- 어디에서 업데이트를 받을 수 있습니다.
    
- 기능 업데이트를 얼마나 자주 사용하겠는가
    
업데이트의 위치를 제어하고 기능 업데이트를 얼마나 자주 받을지 제어할 수 있는 동안 어떤 특정 보안 업데이트나 비보안 업데이트를 선택할 수 없습니다.
  
 **어디에서 업데이트를 받을 수 있습니다.**
  
기본적으로 비즈니스용 Skype 앱을 설치한 후 Microsoft에서 사용할 수 있는 경우 업데이트가 인터넷에서 자동으로 다운로드됩니다. 업데이트가 발생하는 경우 또는 업데이트가 설치된 위치를 더 제어하려는 경우 배포 도구 또는 그룹 Office 정책을 사용하여 구성할 수 있습니다.
  
예를 들어 많은 조직에서 조직 전체에 배포하기 전에 사용자 그룹으로 업데이트를 테스트하려는 경우도 있습니다. 이 작업을 수행하려면 인터넷에서 자동으로 Office 배포 도구 또는 그룹 정책을 사용하여 비즈니스용 Skype 네트워크의 특정 위치에서 업데이트를 받을 수 있도록 앱을 구성할 수 있습니다. 그런 다음, 배포 Office 도구를 사용하여 매월 업데이트를 로컬 네트워크에 다운로드할 수 있습니다.
  
업데이트가 소프트웨어에 대한 Office 365 방법에 대한 자세한 내용은 다음 문서를 참조하세요.
  
- [업데이트 프로세스의 개요 엔터프라이즈용 Microsoft 365 앱](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [업데이트에 대한 업데이트를 관리하는 방법을 엔터프라이즈용 Microsoft 365 앱](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [업데이트 설정 구성 엔터프라이즈용 Microsoft 365 앱](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **기능 업데이트를 얼마나 자주 받을 수 있는가**
  
업데이트를 받을 위치 외에도 클라이언트에 대한 새 기능을 얼마나 자주 받을 수 비즈니스용 Skype 있습니다. 두 가지 선택은 다음과 같습니다.
  
- 새 기능이 있는 경우 매월 기능 업데이트 다운로드
    
- 6개월마다 기능 업데이트 다운로드
    
일부 조직에서는 새 기능을 테스트하는 시간을 원하기 때문에 매월 기능 업데이트를 1년에 두 번만 받을 수 있습니다.
  
업데이트 채널을 구성하는 데 Office 배포 도구 또는 그룹 정책을 사용하여 기능 업데이트를 얼마나 자주 받을 수 있는지 제어할 수 있습니다. 월간 채널은 매월 기능 업데이트를 제공하는 반면, Semi-Annual 채널은 6개월마다 기능 업데이트를 제공합니다. 채널에 대한 자세한 내용은 에 대한 업데이트 [채널 개요를 엔터프라이즈용 Microsoft 365 앱.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>관련 주제

[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)
  
[비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
