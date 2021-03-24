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
description: '소규모, 중소 및 대규모 조직에서 비즈니스용 Skype를 계획하고 배포하고 사용자에게 사용할 수 있도록 하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 7a2ba51a315b77c501735be863f342c1bdb1548f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097294"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365에서 비즈니스용 Skype 클라이언트 배포

이 문서에서는 관리자인 사용자가 **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 조직의 사용자에게 비즈니스용 Skype 앱을 배포하는 방법에 대한 옵션을 설명합니다.
  
비즈니스용 Skype를 사용자에게 배포하기 전에 비즈니스용 Skype Online 설정 문서에서 1-3단계를 [완료해야 합니다.](set-up-skype-for-business-online.md) 이렇게 하면 비즈니스용 Skype가 도메인으로 설정되어 모든 사용자가 라이선스를 가지며, 조직에 대한 [비즈니스용 Skype Online에서](configure-presence-in-skype-for-business-online.md) IM 및 현재 상태 구성을 구성합니다.
  
> [!NOTE]
> 사용자가 비즈니스용 Skype 앱을 설치하려면 PC 또는 디바이스에 로컬 관리자로 설정해야 합니다. 또는 PC 또는 디바이스에 앱을 설치할 수 있는 로컬 그룹에 참여해야 합니다. 사용자가 디바이스에 소프트웨어를 설치할 수 없는 경우 비즈니스용 Skype 앱을 설치해야 합니다. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>대부분의 중소기업의 경우

 **단계별 설치 지침:** 중소기업이 있는 경우 사용자에게 비즈니스용 Skype 앱을 PC에 설치하도록 요청하는 것이 좋습니다. 이러한 지침은 [비즈니스용 Skype 설치 를 지시합니다.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Mac을 사용하는 경우 Office [365용 Mac 2011용 Lync 설정 을 지적합니다.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) 비즈니스용 Skype 앱은 나머지 Office 앱과 별도로 설치됩니다.
  
 엔터프라이즈 고객을 위한 **Microsoft 365 Apps:** 비즈니스에서 엔터프라이즈용 Microsoft 365 Apps(예: E3 요금제)를 포함하는 Office 365 요금제를 사용하는 경우 사용자가 Word, Excel, PowerPoint 등을 다운로드하고 설치하는 동시에 비즈니스용 Skype 앱이 설치됩니다. 또한 Office를 모두 제거하지 않으면 비즈니스용 Skype를 제거할 수 없습니다.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>사용자가 비즈니스용 Skype를 사용할 수 있도록 할지 여부를 선택하세요.

관리자는 [](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) 사용자가 비즈니스용 Skype 앱을 사용할 수 있도록 할지 여부를 선택할 수 있습니다.
  
- **회사의** 모든 사용자가 소프트웨어 : Microsoft 365 관리 센터에 로그인하는지 여부를 제어하려면 내 소프트웨어 설치로 이동한 다음 사용자가 사용할 수 있는 소프트웨어를 선택합니다.
    
    ![회사에 있는 사용자들이 사용할 수 있도록 할 소프트웨어를 선택하십시오.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **회사의** 특정 사용자가 소프트웨어를 받을지 여부를 제어하려면 Microsoft 365 관리 센터에 로그인하려면 **사용자** 활성 사용자로 이동하여 소프트웨어에 대한 액세스 권한을 부여할 사용자를 선택한 다음 제품 라이선스 옆에 있는 편집을 클릭하고 라이선스를 켜거나 끄면  >  됩니다.  
    
    ![사용자가 액세스할 소프트웨어를 선택할 수 있습니다.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 조직의 사용자에게 할당된 계획을 확인해야 하는 경우 Microsoft 365 관리 센터에 로그인하여 사용자 **>**  >  **합니다.** 목록에서 사람을 선택한 다음 제품 라이선스 **아래를 봐야 합니다.** 클래식 관리 센터를 사용하는 경우 할당된 라이선스 **를 살펴 봐야 합니다.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>사용자에게 비즈니스용 Skype를 수동으로 배포
<a name="bkmk_manual_1"> </a>

사용자가 인터넷 대신 네트워크의 위치에서 비즈니스용 Skype 앱을 설치하려면 설치 파일을 다운로드할 수 있습니다. 이렇게하려면 Microsoft 365 관리 센터의 사용자 소프트웨어 수동으로 배포 섹션으로 이동하세요.  그런 다음 설치를 **선택하고** 설치 .exe 파일을 네트워크 위치에 저장할 수 있습니다.
  
또 다른 옵션은 사용자의 비즈니스용 Skype 기본 앱을 다운로드하는 것입니다. 비즈니스용 [Microsoft Skype 기본(32 또는 64비트)을 다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=49440)
  
전체 및 기본 비즈니스용 Skype 앱의 경우 설정 파일을 다운로드한 후 사용자에게 네트워크 경로를 수동으로 보내서 설치 프로그램을 실행하여 해당 컴퓨터에 앱을 설치할 수 있습니다.
  
이러한 다운로드를 사용하여 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 사용자에게 비즈니스용 Skype 앱을 배포할 수도 있습니다.
  
## <a name="for-larger-and-enterprise-organizations"></a>대규모 및 엔터프라이즈 조직의 경우

> [!NOTE]
> 이 섹션은 Office 365 요금제에서 사용할 수 있는 비즈니스용 Skype 앱에만 적용됩니다. 조직에서 MSI(Windows Installer 기반)인 비즈니스용 Skype 앱의 볼륨 사용이 허가된 버전을 사용하는 경우 비즈니스용 Skype Server에서 Windows 클라이언트 설치 사용자 지정을 [참조하세요.](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)
  
많은 기업 또는 대규모 조직에서 사용자는 컴퓨터에 소프트웨어를 설치할 수 없습니다. 대신 IT 부서는 사용자의 컴퓨터에 필요한 소프트웨어를 배포합니다. 또한 IT 부서는 조직에서 사용되는 인터넷 또는 네트워크 대역폭의 양을 제어하기를 원할 수 있으므로 인터넷을 가로질러 또는 회사 네트워크를 가로지르는 대신 네트워크의 가까운 위치에서 소프트웨어를 설치하려는 경우도 있습니다.
  
Office 365에서는 설치 위치를 제어하려는 경우 비즈니스용 Skype 앱을 배포하기 위한 몇 가지 옵션이 있습니다. 이러한 옵션 중 일부는 다음과 같습니다.
  
- 사용자에게 비즈니스용 Skype를 수동으로 배포하는 데 설명된 바와 같이 Microsoft 365 관리 센터에서 비즈니스용 Skype 앱을 로컬 네트워크에 [다운로드합니다.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Office **[배포 도구를](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 사용하여 엔터프라이즈용 Microsoft 365 Apps 또는 비즈니스용 Skype 앱을 로컬 네트워크에 다운로드합니다. 그런 다음 Office 배포 도구를 사용하여 사용자에게 앱을 배포합니다. Office 배포 도구를 사용하면 언어 및 버전(32비트 또는 64비트)과 같은 배포의 특정 측면을 제어할 수 있습니다.
    
- Microsoft 엔드포인트 구성 관리자와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 엔터프라이즈용 Microsoft 365 Apps 또는 비즈니스용 Skype 앱을 사용자에게 배포합니다. Office 배포 도구 또는 [Microsoft](https://go.microsoft.com/fwlink/p/?LinkID=626065) 365 관리 센터에서 다운로드한 소프트웨어와 함께 기존 도구 및 프로세스를 사용할 수 있습니다.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 배포 도구 사용에 대한 자세한 정보

Office 배포 도구 다운로드에 대한 자세한 내용 및 비즈니스용 Skype 앱 및 기타 Office 365 클라이언트 앱 설치에 대한 자세한 내용은 [Office 365의](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)소프트웨어 다운로드 설정 관리를 참조하세요.
  
Office 배포 도구를 사용하여 앱을 배포하는 데 관련된 단계에 대한 개요는 다음과 같습니다.
  
1. Microsoft 다운로드 **[센터에서 최신 Office 배포](https://www.microsoft.com/download/details.aspx?id=49117)** 도구를 다운로드합니다.
    
2. configuration.xml 버전 설정(32비트 또는 64비트), 설치 언어 등 원하는 클라이언트 앱 설정이 있는 Office 배포 도구에서 사용할 파일 만들기
    
3. Office 배포 도구 및 configuration.xml 파일을 사용하여 CDN(Office 콘텐츠 배달 네트워크)에서 로컬 또는 내부 네트워크에 설치 파일을 다운로드합니다.
    
4. Office 배포 도구 및 configuration.xml 비즈니스용 Skype 앱을 포함하여 Office 클라이언트 앱을 설치합니다.
    
Office 배포 도구 및 파일 configuration.xml 자세한 내용은 다음 문서를 참조하세요.
  
- [Office 배포 도구 개요](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml 설정](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Microsoft 엔드포인트 구성 관리자 사용에 대한 자세한 정보

Microsoft 엔드포인트 구성 관리자와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용하여 비즈니스용 Skype 앱을 배포할 수 있습니다. Microsoft 365 관리 센터에서 다운로드한 소프트웨어 또는 Office 배포 도구와 함께 이러한 도구 및 프로세스를 사용할 수 있습니다.
  
Configuration Manager를 사용하여 소프트웨어 배포에 대한 자세한 내용은 다음 문서를 참조하세요.
  
- [Configuration Manager에서 애플리케이션 만들기](/configmgr/apps/deploy-use/create-applications)
    
- [Configuration Manager를 통해 애플리케이션 배포](/configmgr/apps/deploy-use/deploy-applications)
    
엔터프라이즈용 Microsoft 365 Apps 배포의 일환으로 비즈니스용 Skype 앱을 배포하는 경우 Configuration Manager를 사용하여 [엔터프라이즈용 Microsoft 365 앱 관리를 참조하세요.](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>비즈니스용 Skype 앱 업데이트 계획

비즈니스용 Skype 앱을 배포하는 일환으로 비즈니스용 Skype를 설치한 후 업데이트를 받을 방법을 고려해야 합니다. 이러한 업데이트에는 안정성 또는 성능 개선을 제공하는 업데이트와 같은 새로운 기능, 보안 업데이트 또는 비보안 업데이트가 포함됩니다. 고려해야 할 주요 두 가지는 다음과 같습니다.
  
- 어디에서 업데이트를 받을 수 있습니다.
    
- 기능 업데이트를 얼마나 자주 사용하겠는가
    
업데이트의 위치를 제어하고 기능 업데이트를 얼마나 자주 받을지 제어할 수 있는 동안 어떤 특정 보안 업데이트나 비보안 업데이트를 선택할 수 없습니다.
  
 **어디에서 업데이트를 받을 수 있습니다.**
  
기본적으로 비즈니스용 Skype 앱을 설치한 후 Microsoft에서 사용할 수 있는 경우 업데이트가 인터넷에서 자동으로 다운로드됩니다. 업데이트가 발생하는 경우 또는 업데이트가 설치된 위치를 더 제어하려는 경우 Office 배포 도구 또는 그룹 정책을 사용하여 구성할 수 있습니다.
  
예를 들어 많은 조직에서 조직 전체에 배포하기 전에 사용자 그룹으로 업데이트를 테스트하려는 경우도 있습니다. Office 배포 도구 또는 그룹 정책을 사용하여 비즈니스용 Skype 앱을 구성하여 인터넷에서 자동으로 업데이트하는 대신 네트워크의 특정 위치에서 업데이트를 받을 수 있습니다. 그런 다음 Office 배포 도구를 사용하여 매월 업데이트를 로컬 네트워크에 다운로드할 수 있습니다.
  
Office 365 소프트웨어의 업데이트 작동 방식에 대한 자세한 내용은 다음 문서를 참조하세요.
  
- [엔터프라이즈용 Microsoft 365 Apps의 업데이트 프로세스 개요](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [엔터프라이즈용 Microsoft 365 Apps에 대한 업데이트를 관리하는 방법 선택](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [엔터프라이즈용 Microsoft 365 Apps에 대한 업데이트 설정 구성](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **기능 업데이트를 얼마나 자주 받을 수 있는가**
  
업데이트를 받을 위치 외에도 비즈니스용 Skype 클라이언트에 대한 새 기능을 얼마나 자주 받을지 제어할 수도 있습니다. 두 가지 선택은 다음과 같습니다.
  
- 새 기능이 있는 경우 매월 기능 업데이트 다운로드
    
- 6개월마다 기능 업데이트 다운로드
    
일부 조직에서는 새 기능을 테스트하는 시간을 원하기 때문에 매월 기능 업데이트를 1년에 두 번만 받을 수 있습니다.
  
Office 배포 도구 또는 그룹 정책을 사용하여 업데이트 채널을 구성하여 기능 업데이트를 얼마나 자주 받을지 제어할 수 있습니다. 월간 채널은 매월 기능 업데이트를 제공하는 반면, Semi-Annual 채널은 6개월마다 기능 업데이트를 제공합니다. 채널에 대한 자세한 내용은 [엔터프라이즈용 Microsoft 365 Apps의 업데이트 채널 개요를 참조하세요.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)
  
[비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
