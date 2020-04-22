---
title: 비즈니스용 Skype 서버에 대 한 클라이언트 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '요약: 비즈니스용 Skype에 대 한 엔터프라이즈 클라이언트 설치 방법에 대해 간략하게 설명 합니다.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778284"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 클라이언트 배포
 
**요약:** 비즈니스용 Skype에 대 한 엔터프라이즈 클라이언트 설치 방법 개요
  
비즈니스용 Skype를 사용자에 게 배포 하는 방법은 Office 365 계획의 일부로 비즈니스용 Skype를 구매한 경우 또는 볼륨 라이선스 버전의 비즈니스용 Skype를 구매한 경우에 따라 달라 집니다. 
  
- **Office 365** 비즈니스용 Skype를 포함 하는 Office 365 요금제가 있는 경우 사용 되는 설치 기술을 간편 실행 이라고 합니다. Office 365를 사용 하 여 Microsoft 365 관리 센터에서 사용자를 위해 비즈니스용 Skype를 설치 하도록 할 수 있습니다. 또는 소프트웨어를 로컬 네트워크에 다운로드 한 다음 Microsoft 끝점 구성 관리자와 같은 기존 소프트웨어 배포 도구를 사용 하 여 비즈니스용 Skype를 사용자에 게 배포할 수 있습니다. Office 365와 함께 제공 되는 비즈니스용 Skype에 대 한 설치 정보를 보려면 [office 365에서 비즈니스용 skype 클라이언트 배포](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)를 참조 하세요.
    
- **볼륨 라이선스** 볼륨 라이선스 버전의 비즈니스용 Skype 2015 또는 2016 클라이언트를 보유 하는 경우 사용 되는 설치 기술은 Windows Installer (MSI)입니다. Windows Installer 기반 설치 패키지는 여러 개의 MSI 파일로 구성 됩니다. 언어 중립적인 핵심 MSI 패키지는 완벽한 제품 구성을 위해 하나 이상의 언어별 패키지로 조합됩니다. 설치 프로그램은 개별 패키지를 조합하고 사용자 컴퓨터에 Office를 설치하는 동안 그리고 설치 후에 사용자 지정 및 유지 관리 작업을 수행합니다. 비즈니스용 Skype 2019 클라이언트는 간편 실행 설치 관리자를 사용 합니다.
    
이 섹션의 항목에서는 Windows Installer를 사용 하 고 사용자 지정 하 여 일반 절차를 통해 비즈니스용 Skype 클라이언트를 사용자에 게 배포 하는 방법에 대해 설명 합니다.
  
> [!NOTE]
> Outlook 메시징 및 공동 작업 클라이언트에서 모임 관리를 지 원하는 Microsoft Office 용 Skype 모임 추가 기능이 비즈니스용 Skype 클라이언트에 자동으로 설치 됩니다. 
  
> [!NOTE]
> Office 365 설치 프로그램은 이전 버전의 Lync를 제거 하지 않습니다. 비즈니스용 Skype 클라이언트는 다른 Lync 클라이언트와 나란히 설치 됩니다. 
  
## <a name="installing-windows-clients"></a>Windows 클라이언트 설치

- [비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정](customize-windows-client-installation.md)
    
- [비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성](configure-the-client-experience.md)
    
- [비즈니스용 Skype 서버에서 스마트 연락처 목록 구성](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>장치 클라이언트 설치

- [Windows Phone 용 비즈니스용 Skype 설치 및 테스트](windows-phone.md)
    
- [IOS 용 비즈니스용 Skype 설치 및 테스트](ios.md)
    
    
- [비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포](deploy-the-lync-vdi-plug-in.md)
    
- [비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](deploy-web-downloadable-clients.md)
    
- [비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>참고 항목

[Office 365에서 비즈니스용 Skype 클라이언트 배포](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
