---
title: 비즈니스용 Skype 서버용 클라이언트 배포
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '요약: 비즈니스용 Skype의 엔터프라이즈 클라이언트 설치 방법 개요.'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805698"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 클라이언트 배포
 
**요약:** 비즈니스용 Skype의 엔터프라이즈 클라이언트 설치 방법 개요
  
사용자에게 비즈니스용 Skype를 배포하는 방법은 비즈니스용 Skype를 Microsoft 365 또는 Office 365 요금제의 일부로 구입한지 아니면 비즈니스용 Skype 볼륨 라이선스 버전을 구매한지 여부에 따라 결정됩니다. 
  
- **Microsoft 365 또는 Office 365** 비즈니스용 Skype를 포함하는 Microsoft 365 또는 Office 365 요금제가 있는 경우 사용되는 설치 기술을 Click-to-Run이라고 합니다. 사용자가 Microsoft 365 관리 센터에서 비즈니스용 Skype를 직접 설치하도록 할 수 있습니다. 또는 소프트웨어를 로컬 네트워크에 다운로드한 다음 Microsoft Endpoint Configuration Manager와 같은 기존 소프트웨어 배포 도구를 사용하여 사용자에게 비즈니스용 Skype를 배포할 수 있습니다. Microsoft 365 및 Office 365와 함께 제공된 비즈니스용 Skype에 대한 설치 정보는 [Microsoft 365 또는 Office 365에서](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)비즈니스용 Skype 클라이언트 배포를 참조하세요.
    
- **볼륨 라이선스** 볼륨 라이선스 버전의 비즈니스용 Skype 2015 또는 2016 클라이언트가 있는 경우 사용되는 설치 기술은 Windows Installer(MSI)입니다. Windows Installer 기반 설치 패키지는 여러 MSI 파일로 구성됩니다. 언어 중립적인 핵심 MSI 패키지는 완벽한 제품 구성을 위해 하나 이상의 언어별 패키지로 조합됩니다. 설치 프로그램은 개별 패키지를 조합하고 사용자 컴퓨터에 Office를 설치하는 동안 그리고 설치 후에 사용자 지정 및 유지 관리 작업을 수행합니다. 비즈니스용 Skype 2019 클라이언트는 Click-to-Run 설치 관리자를 사용 합니다.
    
이 섹션의 항목에서는 일반 절차를 통해 사용자에게 비즈니스용 Skype 클라이언트를 배포하도록 Windows Installer를 사용하고 사용자 지정하는 방법을 설명합니다.
  
> [!NOTE]
> Outlook 메시징 Microsoft Office 공동 작업 클라이언트 내에서 모임 관리를 지원하는 비즈니스용 Skype 모임 추가 기능을 비즈니스용 Skype 클라이언트와 함께 자동으로 설치합니다. 
  
> [!NOTE]
> Microsoft 365 및 Office 365 설치 프로그램은 이전 버전의 Lync를 제거하지 않습니다. 비즈니스용 Skype 클라이언트는 다른 Lync 클라이언트와 함께 나란히 설치됩니다. 
  
## <a name="installing-windows-clients"></a>Windows 클라이언트 설치

- [비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정](customize-windows-client-installation.md)
    
- [비즈니스용 Skype를 통해 클라이언트 환경 구성](configure-the-client-experience.md)
    
- [비즈니스용 Skype 서버에서 스마트 연락처 목록 구성](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>장치 클라이언트 설치

- [Windows Phone용 비즈니스용 Skype 설치 및 테스트](windows-phone.md)
    
- [iOS용 비즈니스용 Skype 설치 및 테스트](ios.md)
    
    
- [비즈니스용 Skype 서버를 통해 Lync VDI 플러그 인 배포](deploy-the-lync-vdi-plug-in.md)
    
- [비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](deploy-web-downloadable-clients.md)
    
- [비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>참고 항목

[Microsoft 365 또는 Office 365에서 비즈니스용 Skype 클라이언트 배포](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
