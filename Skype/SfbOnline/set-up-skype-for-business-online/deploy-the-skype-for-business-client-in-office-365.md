---
title: Office 365에서 비즈니스용 Skype 클라이언트 배포
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
description: '중소 규모의 대규모 조직에서 비즈니스용 Skype를 계획 하 고 배포 하 고 사용자가 사용할 수 있도록 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 052cc4cb8aa1242628e0f57a57a3fe5532be3d71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706503"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Office 365에서 비즈니스용 Skype 클라이언트 배포

이 문서에서는 **[관리자](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 가 비즈니스용 Skype 앱을 조직의 사용자에 게 배포할 수 있는 방법에 대 한 옵션에 대해 설명 합니다.
  
비즈니스용 Skype를 사용자에 게 배포 하기 전에 비즈니스용 [Skype Online 설정](set-up-skype-for-business-online.md)문서에서 1-3 단계를 완료 했는지 확인 합니다. 이렇게 하면 비즈니스용 Skype가 도메인에 설정 되 고, 모든 사용자는 자신의 라이선스를 보유 하 고 있으며, 메신저를 구성 하 고 [비즈니스용 Skype Online에서 조직의 현재 상태를 구성할](configure-presence-in-skype-for-business-online.md) 수 있습니다.
  
> [!NOTE]
> 사용자가 비즈니스용 Skype 앱을 설치 하려면 해당 PC 또는 장치에서 로컬 관리자 여야 합니다. 또는 PC 또는 장치에 앱을 설치할 수 있는 로컬 그룹의 일부일 필요 합니다. 사용자가 디바이스에 소프트웨어를 설치할 수 없는 경우 비즈니스용 Skype 앱을 설치 해야 합니다. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>중소 규모 기업

 단계별 **설치 지침:** 중소 규모의 비즈니스가 있는 경우, 사용자에 게 자신의 PC에 비즈니스용 Skype 앱을 설치 하도록 요청 하는 것이 좋습니다. 이 지침을 가리키면 [비즈니스용 Skype를 설치](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)합니다. Mac을 사용 하는 경우 [mac 용 Lync 2011 For Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)를 가리키도록 설정 합니다. 비즈니스용 Skype 앱은 나머지 Office 앱과 별도로 설치 됩니다.
  
 **Office 365 ProPlus 고객:** 앱이 E3 계획과 같은 Office 365 ProPlus를 포함 하는 Office 365 계획을 사용 하는 경우 비즈니스용 Skype 앱은 사용자가 Word, Excel, PowerPoint 등을 다운로드 하 고 설치 하는 동시에 설치 됩니다. 이는 또한 모든 Office를 제거 하지 않는 한 비즈니스용 Skype를 제거할 수 없음을 의미 합니다.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>비즈니스용 Skype를 사용자가 사용할 수 있도록 설정할지 여부 선택

[관리자](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) 는 비즈니스용 Skype 앱을 사용자가 사용할 수 있도록 설정할지 여부를 선택할 수 있습니다.
  
- **회사의 모든 사용자가 소프트웨어를 받을지 여부를 제어 하려면**Microsoft 365 관리 센터에 로그인 하 고 **소프트웨어 설치**로 이동한 다음 사용자에 게 제공 하려는 소프트웨어를 선택 합니다.
    
    ![회사의 사용자가 사용할 수 있도록 설정할 소프트웨어를 선택 합니다.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **회사의 특정 사용자가 소프트웨어를 받을 수 있는지 제어 하려면**Microsoft 365 관리 센터에 로그인 하 여 **사용자** > **활성 사용자**로 이동 하 고 소프트웨어에 대 한 액세스 권한을 부여할 사용자를 선택한 다음 **제품 라이선스** 옆에 있는 **편집** 을 클릭 하 고 라이선스를 설정 하거나 해제 합니다.
    
    ![사용자가 액세스 하는 데 사용할 소프트웨어를 선택 합니다.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 조직의 사용자에 게 할당 된 계획을 확인 해야 하는 경우 **사용자** > **활성 사용자**> Microsoft 365 관리 센터에 로그인 합니다. 목록에서 사용자를 선택 하 고 **제품 라이선스**를 확인 합니다. 클래식 관리 센터를 사용 하는 경우 **할당 된 라이선스**를 확인 합니다. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>수동으로 비즈니스용 Skype를 사용자에 게 배포
<a name="bkmk_manual_1"> </a>

사용자가 인터넷이 아닌 네트워크 위치에서 비즈니스용 Skype 앱을 설치 하도록 하려면 설치 파일을 다운로드할 수 있습니다. 이렇게 하려면 Microsoft 365 관리 센터의 **사용자 소프트웨어 수동 배포** 섹션을 참조 하세요. 그런 다음 **설치** 를 선택 하 고 네트워크 위치에 setup.exe 파일을 저장할 수 있습니다.
  
다른 옵션은 비즈니스용 Skype Basic 앱을 사용자에 게 다운로드 하는 것입니다. [Microsoft 비즈니스용 Skype Basic (32 또는 64 비트)](https://www.microsoft.com/download/details.aspx?id=49440)을 다운로드할 수 있습니다.
  
설치 파일을 다운로드 한 후에는 전체 및 기본 비즈니스용 Skype 앱에 대해 사용자가 설치 프로그램을 실행 하 여 컴퓨터에 앱을 설치할 수 있도록 네트워크 경로를 수동으로 전송 해야 합니다 (예: 전자 메일).
  
이러한 다운로드를 사용 하 여 기존 소프트웨어 배포 도구 및 프로세스를 사용 하 여 비즈니스용 Skype 앱을 사용자에 게 배포할 수도 있습니다.
  
## <a name="for-larger-and-enterprise-organizations"></a>대규모 및 엔터프라이즈 조직의 경우

> [!NOTE]
> 이 섹션은 Office 365 계획을 통해 제공 되는 비즈니스용 Skype 앱에만 적용 됩니다. 조직에서 Windows Installer 기반 비즈니스용 Skype 앱의 볼륨 라이선스 버전을 사용 하는 경우 비즈니스용 [Skype 서버에서 windows 클라이언트 설치 사용자 지정](https://technet.microsoft.com/library/jj204934.aspx)을 참조 하세요.
  
여러 기업 또는 대규모 조직에서는 사용자가 자신의 컴퓨터에 소프트웨어를 설치할 수 없습니다. 대신 IT 부서가 사용자의 컴퓨터에 필요한 소프트웨어를 배포 합니다. 또한 IT 부서는 조직에서 사용 하는 인터넷 또는 네트워크 대역폭의 양을 제어 하 고 인터넷 이나 회사 네트워크를 통해 네트워크 상에 서 가까운 위치에서 소프트웨어를 설치 하려고 합니다.
  
Office 365를 사용 하면 비즈니스용 Skype 앱을 배포 하기 위한 여러 옵션을 사용할 수 있습니다 (설치 위치를 제어 하려는 경우). 이러한 옵션에는 다음이 포함 됩니다.
  
- 비즈니스용 [skype를 사용자에 게 수동으로 배포 하는 방법](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)에 설명 된 바와 같이, Microsoft 365 관리 센터에서 로컬 네트워크에 비즈니스용 skype 앱을 다운로드 하세요.
    
- Office **[배포 도구](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 를 사용 하 여 Office 365 ProPlus 또는 비즈니스용 Skype 앱을 로컬 네트워크에 다운로드 합니다. 그런 다음 Office 배포 도구를 사용 하 여 앱을 사용자에 게 배포 합니다. Office 배포 도구를 사용 하면 언어 및 버전 (32 비트 또는 64 비트)과 같은 배포의 특정 측면을 제어할 수 있습니다.
    
- Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용 하 여 Office 365 ProPlus 또는 비즈니스용 Skype 앱을 사용자에 게 배포 합니다. [Office 배포 도구](https://go.microsoft.com/fwlink/p/?LinkID=626065) 또는 Microsoft 365 관리 센터에서 다운로드 한 소프트웨어를 사용 하 여 기존 도구 및 프로세스를 사용할 수 있습니다.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 배포 도구 사용에 대 한 자세한 정보

Office 배포 도구 다운로드에 대 한 자세한 내용과 비즈니스용 Skype 앱 및 기타 Office 365 클라이언트 앱을 설치 하는 방법에 대 한 자세한 내용은 [office 365의 소프트웨어 다운로드 설정 관리](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)를 참조 하세요.
  
다음은 Office 배포 도구를 사용 하 여 앱을 배포 하는 데 관련 된 단계를 간략하게 설명 합니다.
  
1. Microsoft 다운로드 센터에서 **[최신 Office 배포 도구를 다운로드](https://www.microsoft.com/download/details.aspx?id=49117)** 합니다.
    
2. 버전 (32 비트 또는 64 비트), 설치 언어 등의 원하는 클라이언트 앱 설정이 있는 Office 배포 도구에서 사용할 구성 .xml 파일을 만듭니다.
    
3. Office 배포 도구 및 구성 .xml 파일을 사용 하 여 Office CDN (콘텐츠 배달 네트워크)에서 로컬 또는 내부 네트워크에 설정 파일을 다운로드 합니다.
    
4. Office 배포 도구 및 .xml을 사용 하 여 비즈니스용 Skype 앱을 비롯 한 Office 클라이언트 앱을 설치 합니다.
    
Office 배포 도구 및 구성 .xml 파일을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.
  
- [Office 배포 도구 개요](https://technet.microsoft.com/library/jj219422.aspx)
    
- [구성 xml 설정](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Microsoft 끝점 구성 관리자 사용에 대 한 자세한 정보

Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구 및 프로세스를 사용 하 여 비즈니스용 Skype 앱을 배포할 수 있습니다. Microsoft 365 관리 센터에서 다운로드 하는 소프트웨어 또는 Office 배포 도구를 사용 하 여 이러한 도구 및 프로세스를 사용할 수 있습니다.
  
Configuration Manager를 사용 하 여 소프트웨어를 배포 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.
  
- [Configuration Manager에서 응용 프로그램 만들기](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Configuration Manager를 사용 하 여 응용 프로그램 배포](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Office 365 ProPlus 배포의 일부로 비즈니스용 Skype 앱을 배포 하는 경우 [구성 관리자를 사용 하 여 Office 365 ProPlus 관리](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)를 참조 하세요.
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>비즈니스용 Skype 앱 업데이트 계획

비즈니스용 skype 앱을 배포 하는 과정의 일환으로 비즈니스용 Skype가 설치 된 후 업데이트를 받는 방법을 고려해 야 합니다. 이러한 업데이트에는 안정성 또는 성능 개선을 제공 하는 업데이트와 같은 새로운 기능, 보안 업데이트 또는 비보안 업데이트 등이 포함 될 수 있습니다. 고려해 야 할 두 가지 주요 사항은 다음과 같습니다.
  
- 업데이트를 받을 위치
    
- 기능 업데이트를 얼마나 자주 받을 지를 선택 합니다.
    
업데이트를 받을 위치 및 기능 업데이트를 받을 빈도를 제어할 수 있지만, 어떤 경우에는 어떤 보안 업데이트나 업데이트를 받을 수 없습니다.
  
 **업데이트를 받을 위치**
  
기본적으로 비즈니스용 Skype 앱이 설치 된 후에는 Microsoft에서 제공 되는 업데이트가 인터넷에서 자동으로 다운로드 됩니다. 업데이트가 발생 하는 시기 또는 업데이트가 설치 되는 위치를 보다 효율적으로 제어 하려면 Office 배포 도구 또는 그룹 정책을 사용 하 여 해당 구성을 구성할 수 있습니다.
  
예를 들어 조직 전체에 배포 하기 전에 많은 조직이 사용자 그룹을 사용 하 여 업데이트를 테스트 하려고 합니다. Office 배포 도구 또는 그룹 정책을 사용 하 여 비즈니스용 Skype 앱을 구성 하 여 인터넷에서 자동이 아닌 네트워크의 특정 위치에서 업데이트를 받을 수 있습니다. 그런 다음 Office 배포 도구를 사용 하 여 매달 업데이트를 로컬 네트워크에 다운로드할 수 있습니다.
  
Office 365 소프트웨어에 대 한 업데이트가 작동 하는 방식에 대 한 자세한 내용은 다음 문서를 참조 하세요.
  
- [Office 365 ProPlus의 업데이트 프로세스 개요](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Office 365 ProPlus에 대 한 업데이트를 관리 하는 방법 선택](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Office 365 ProPlus에 대 한 업데이트 설정 구성](https://technet.microsoft.com/library/dn761708.aspx)
    
  **기능 업데이트를 얻는 빈도**
  
업데이트를 받을 수 있는 위치 외에도 비즈니스용 Skype 클라이언트에 대 한 새로운 기능을 받을 빈도를 제어할 수 있습니다. 두 가지 선택 옵션은 다음과 같습니다.
  
- 새로운 기능이 있는 경우 매달 기능 업데이트 받기
    
- 6 개월 마다 기능을 업데이트 하세요.
    
일부 조직의 경우 새 기능을 테스트 하는 데 시간이 필요 하므로, 매월 1 년이 아닌 두 번의 기능 업데이트를 받게 됩니다.
  
Office 배포 도구 또는 그룹 정책을 사용 하 여 업데이트 채널을 구성 하 여 기능 업데이트를 받을 빈도를 제어할 수 있습니다. 월 단위 채널은 월간 업데이트 기능을 제공 하는 반면, 반기 채널은 6 개월 마다 기능을 업데이트할 수 있도록 합니다. 채널에 대 한 자세한 내용은 [Office 365 ProPlus의 업데이트 채널 개요](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)를 참조 하세요.
  
## <a name="related-topics"></a>관련 주제

[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)
  
[비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
