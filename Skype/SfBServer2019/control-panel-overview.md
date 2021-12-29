---
title: 제어판 - 개요
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 이 문서에서는 새로운 제어판에 대한 개요를 제공합니다.
ms.openlocfilehash: 7def5267b88260b66b6aa345c9585b83659f6ea3
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61625939"
---
# <a name="control-panel"></a>제어판

현재 제어판은 새로운 버전의 레거시 제어판으로, 함께 존재합니다. 새 제어판은 2019년 7월 누적 업데이트에서 출시되었습니다. 조직의 환경에서 서버, 사용자, 클라이언트 및 장치의 구성을 관리하는 데 도움이 됩니다.

레거시 제어판은 Silverlight 기술이 2021년 10월 12일 "지원 종료" 단계에 도달한 경우 작동하지 않을 수 있습니다. 자세한 내용은 [Silverlight 지원 종료를 참조하세요.](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)

> [!NOTE]
> 레거시 제어판에 대한 [](../SfbServer/management-tools/install-and-open-administrative-tools.md)자세한 내용은 **제어판 을** 참조하고 제어판의 비즈니스용 Skype 서버 이동합니다.

## <a name="access-control-panel"></a>액세스 제어판

브라우저에서 새 제어판을 시작하도록 https:// &lt; pool-FQDN /macp 또는 구성된 단순 &gt; URL을 입력합니다.

새 제어판에는 조직의 대부분의 요구 사항을 다루는 일반적으로 사용되는 메뉴 항목이 포함되어 있습니다. 새 제어판에서 사용할 수 없는 레거시 제어판의 몇 가지 메뉴 항목이 있습니다. 그러나 사용자가 PowerShell cmdlet을 통해 해당 메뉴 항목의 기능을 사용할 수 있는 옵션이 있습니다. 자세한 내용은 아래 표를 참조하세요.

> [!NOTE]
> 다른 메뉴 항목에 대한 설명서는 단계적 방식으로 이후에 사용할 수 있습니다.

## <a name="client"></a>클라이언트

|하위 메뉴  |cmdlet에 대한 정보 원본  |
|---------|---------|
|클라이언트 버전 정책         |    [클라이언트 버전 정책](use-powershell-client-menu.md#client-version-policy)     |
|클라이언트 버전 구성      |  [클라이언트 버전 구성](use-powershell-client-menu.md#client-version-configuration)       |
|장치 업데이트    | [장치 업데이트](use-powershell-client-menu.md#device-update)        |
|테스트 장치     | [장치 테스트](use-powershell-client-menu.md#test-device)        |
|장치 로그 구성         |    [장치 로그 구성](use-powershell-client-menu.md#device-log-configuration)     |
|장치 구성         |    [장치 구성](use-powershell-client-menu.md#device-configuration)     |
|모바일 정책         |    [모바일 정책](use-powershell-client-menu.md#mobility-policy)     |
|푸시 알림 구성         |    [푸시 알림 구성](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>보안

|하위 메뉴  |cmdlet에 대한 정보 원본  |
|---------|---------|
|등록자         |    [등록자](use-powershell-security-menu.md#registrar)     |
|웹 서비스      |  [웹 서비스](use-powershell-security-menu.md#web-service)       |
|PIN 정책    | [PIN 정책](use-powershell-security-menu.md#pin-policy)        |

## <a name="im-and-presence"></a>IM 및 현재 상태

|하위 메뉴  |cmdlet에 대한 정보 원본  |
|---------|---------|
|파일 필터         |    [파일 필터](use-powershell-im-and-presence-menu.md#file-filter)     |
|URL 필터      |  [URL 필터](use-powershell-im-and-presence-menu.md#url-filter)       |

## <a name="monitoring-and-archiving"></a>모니터링 및 보관

|하위 메뉴  |cmdlet에 대한 정보 원본  |
|---------|---------|
|통화 정보 기록       |    [통화 세부 정보 녹음](use-powershell-monitoring-and-archiving-menu.md#call-detail-recording)     |
|경험 품질 데이터      |  [경험 품질 데이터](use-powershell-monitoring-and-archiving-menu.md#quality-of-experience-data)       |
|보관 정책       |    [보관 정책](use-powershell-monitoring-and-archiving-menu.md#archiving-policy)     |
|보관 구성      |  [보관 구성](use-powershell-monitoring-and-archiving-menu.md#archiving-configuration)       |

## <a name="network-configuration"></a>네트워크 구성

|하위 메뉴  |cmdlet에 대한 정보 원본  |
|---------|---------|
|위치 정책       |    [위치 정책](use-powershell-network-configuration-menu.md#location-policy)     |
|대역폭 정책      |  [대역폭 정책](use-powershell-network-configuration-menu.md#bandwidth-policy)       |
|지역       |    [지역](use-powershell-network-configuration-menu.md#region)     |
|사이트      |  [Site](use-powershell-network-configuration-menu.md#site)       |
|서브넷      |  [서브넷](use-powershell-network-configuration-menu.md#subnet)       |
|지역 링크       |    [지역 링크](use-powershell-network-configuration-menu.md#region-link)     |
|지역 경로      |  [지역 경로](use-powershell-network-configuration-menu.md#region-route)       |

## <a name="topology"></a>토폴로지

|하위 메뉴  |cmdlet에 대한 정보 원본  |
|---------|---------|
|상태       |    [상태](use-powershell-topology-menu.md#status)     |
|서버 응용 프로그램      |  [서버 응용 프로그램](use-powershell-topology-menu.md#server-application)       |
|단순 URL       |    [단순 URL](use-powershell-topology-menu.md#simple-url)     |
|신뢰할 수 있는 응용 프로그램       |    [신뢰할 수 있는 응용 프로그램](use-powershell-topology-menu.md#trusted-application)     |
