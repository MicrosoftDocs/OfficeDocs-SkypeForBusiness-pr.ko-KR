---
title: 비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '요약: 비즈니스용 Skype의 설치 방법 및 도구에 대한 개요입니다.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805718"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Windows 클라이언트 설치 사용자 지정
 
**요약:** 비즈니스용 Skype의 설치 방법 및 도구 개요.
  
> [!NOTE]
> Microsoft 365 및 Office 365와 함께 제공된 비즈니스용 Skype에 대한 설치 정보는 [Microsoft 365 또는 Office 365에서](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)비즈니스용 Skype 클라이언트 배포를 참조하세요. 
  
엔터프라이즈 관리자는 이 섹션에서 설명하는 방법을 사용하여 볼륨 라이선스 버전의 비즈니스용 Skype에 대한 Windows Installer 기반(.msi) 설치를 사용자 지정할 수 있습니다. 모든 사용자 지정 옵션을 제공하는 단일 도구가 아니기 때문에 비즈니스용 Skype 배포에서 이러한 방법의 조합을 사용할 수 있습니다. 다음 섹션에 설명된 도구를 사용할 수 있습니다.
  
- 비즈니스용 Skype 서버의 [OCT(Office](use-the-office-customization-tool-oct.md) 사용자 지정 도구)를 사용하여 비즈니스용 Skype 및 기타 Office 프로그램의 설정 옵션과 기능을 사용자 지정합니다.
    
- [이 Config.xml](use-config-xml-to-perform-installation-tasks.md) 사용하여 비즈니스용 Skype 서버에서 설치 작업을 수행하여 네트워크 설치 지점의 경로를 지정하고 자동 설치를 수행합니다.
    
- [비즈니스용 Skype 서버의](use-setup-command-line-options.md) 설치 명령줄 옵션을 사용하여 설치 중에 사용할 Config.xml 파일을 지정합니다.
    
- [그룹 정책 개체](configure-client-bootstrapping-policies.md) 편집기 MMC 스냅인을 사용하여 비즈니스용 Skype 서버에서 클라이언트 부트스트래프 정책을 구성합니다.
    
Office 제품군을 배포할 때 구성할 다른 옵션이 있을 수 있습니다. 이 섹션의 항목에서는 이러한 사용자 지정 도구에 대해 간략하게 설명하고 비즈니스용 Skype와 관련한 고려 사항을 설명합니다. 각 도구에 대한 자세한 Office 도움말 링크도 포함됩니다. 
  

