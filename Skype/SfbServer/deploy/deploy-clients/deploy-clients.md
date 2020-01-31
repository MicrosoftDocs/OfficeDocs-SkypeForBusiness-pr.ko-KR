---
title: 비즈니스용 Skype 서버용 클라이언트 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: '요약: 비즈니스용 Skype의 엔터프라이즈 클라이언트 설치 방법 개요.'
ms.openlocfilehash: b791a4f460eaeac86345eae8896046d90d88831b
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628294"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 클라이언트 배포
 
**요약:** 비즈니스용 Skype에 대 한 엔터프라이즈 클라이언트 설치 방법 개요.
  
비즈니스용 Skype를 사용자에 게 배포 하는 방법은 Office 365 계획의 일부로 비즈니스용 Skype를 구입 했는지에 따라, 볼륨 라이선스 버전의 비즈니스용 Skype를 구입 하는 것입니다. 
  
- **Office 365** 비즈니스용 Skype를 포함 하는 Office 365 계획이 있는 경우 사용 되는 설치 기술을 간편 실행 이라고 합니다. Office 365를 사용 하면 Office 365 포털에서 사용자가 비즈니스용 Skype를 설치 하도록 할 수 있습니다. 또는 소프트웨어를 로컬 네트워크에 다운로드 한 다음 Microsoft 끝점 구성 관리자와 같은 기존 소프트웨어 배포 도구를 사용 하 여 사용자에 게 비즈니스용 Skype를 배포할 수 있습니다. Office 365와 함께 제공 되는 비즈니스용 Skype에 대 한 설치 정보는 [office 365의 비즈니스용 skype 클라이언트 배포](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)를 참조 하세요.
    
- **볼륨 라이선스** 볼륨 라이선스 버전의 비즈니스용 Skype 2015 또는 2016 클라이언트를 보유 하 고 있는 경우 사용 되는 설치 기술은 Windows Installer (MSI)입니다. Windows Installer 기반 설치 패키지는 여러 개의 MSI 파일로 구성 됩니다. 언어 중립적인 핵심 MSI 패키지는 완전 한 제품을 만들기 위해 하나 이상의 언어별 패키지와 결합 됩니다. 설치 프로그램은 개별 패키지를 조립 하 고 사용자의 컴퓨터에 Office를 설치 하는 동안과 사용자 지정 및 유지 관리 작업을 수행 합니다. 비즈니스용 Skype 2019 클라이언트는 간편 실행 설치 관리자를 사용 합니다.
    
이 섹션의 항목에서는 Windows Installer를 사용 하 고 사용자 지정 하 여 일반 절차를 통해 비즈니스용 Skype 클라이언트를 배포 하는 방법에 대해 설명 합니다.
  
> [!NOTE]
> Outlook messaging 및 공동 작업 클라이언트 내에서 모임 관리를 지 원하는 Microsoft Office 용 Skype 모임 추가 기능이 비즈니스용 Skype 클라이언트에 자동으로 설치 됩니다. 
  
> [!NOTE]
> Office 365 설치 프로그램이 이전 버전의 Lync를 제거 하지 않습니다. 비즈니스용 Skype 클라이언트는 다른 Lync 클라이언트와 나란히 설치 됩니다. 
  
## <a name="installing-windows-clients"></a>Windows 클라이언트 설치

- [비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정](customize-windows-client-installation.md)
    
- [비즈니스용 Skype에서 클라이언트 환경 구성](configure-the-client-experience.md)
    
- [비즈니스용 Skype 서버의 스마트 연락처 목록 구성](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>장치 클라이언트 설치

- [Windows Phone 용 비즈니스용 Skype 설치 및 테스트](windows-phone.md)
    
- [IOS 용 비즈니스용 Skype 설치 및 테스트](ios.md)
    
    
- [비즈니스용 Skype 서버를 사용 하 여 Lync VDI 플러그 인 배포](deploy-the-lync-vdi-plug-in.md)
    
- [비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포](deploy-web-downloadable-clients.md)
    
- [비즈니스용 Skype에서 Mac 클라이언트 환경 사용자 지정](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>참고 항목

[Office 365에서 비즈니스용 Skype 클라이언트 배포](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
