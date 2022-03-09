---
title: 사용자 Windows 업데이트 Microsoft Teams 룸
ms.author: serdars
author: SerdarSoysal
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: M365-voice
ms.assetid: ''
description: 사용자 Windows 업데이트 Microsoft Teams 룸
ms.openlocfilehash: 1f5e297e699b4a6bc318f2ab7f2de6697cafada3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402882"
---
# <a name="manage-windows-updates"></a>업데이트 Windows 관리

Microsoft Teams 룸 IoT Windows 10 Enterprise VL(Windows 10 Enterprise)에서 실행되어 표준 데스크톱과 동일한 Windows 업데이트 및 OS 빌드를 수신합니다.

Windows 업데이트는 다음과 같은 몇 가지 방법으로 관리할 수 있습니다.

## <a name="hands-off-approach"></a>손 끄기 방법 
- 업데이트는 업데이트에서 직접 다운로드할 수 Windows 시간 동안 설치할 수 있습니다. 구성을 변경하지 않았다면 이 상태가 기본 상태입니다.
- 지연되지 않는 업데이트는 릴리스 1일이 자동으로 설치됩니다. 
- 품질 업데이트 및 드라이버는 1일 자동으로 다운로드하여 설치합니다. 
- 기능 업데이트 아래 추가 참고를 참조하세요. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[Windows 업데이트(](/windows/deployment/update/waas-manage-updates-wufb)GPO 또는 Intune)   
- 업데이트는 WU 또는 WSUS에서 다운로드되지만 KB의 원래 릴리스 날짜를 지난 구성된 지연으로 다운로드됩니다. 
- 여러 OU 또는 필터링된 정책과 결합하여 배포 "링"을 만들 수 있습니다. 여기서 관리자는 먼저 품질 업데이트를 설치하는 장치와 나중에 설치할 장치를 지정할 수 있습니다. 이렇게 하면 전체 배포에서 업데이트를 롤아웃하기 전에 시스템의 하위 집합에 대한 안정성 및 성능 테스트를 수행하여 Windows 업데이트 관리에 대한 오버헤드를 Microsoft Endpoint Configuration Manager 있습니다.
- 대역폭 관리 Windows 비즈니스용 업데이트가 제공하는 제어를 원하는 경우 [](/windows/deployment/update/waas-integrate-wufb) WSUS 및 비즈니스용 Windows 구성할 수 있습니다.
- 기능 업데이트. 아래 추가 참고를 참조하세요.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- 비즈니스용 Windows 업데이트와 마찬가지로 각 "링" 또는 전체 배포 내에서 특정 KB의 대상을 지정하는 추가 옵션도 있습니다. 각 업데이트는 지연에만 사용되지 않고 개별적으로 배포 및 테스트할 수 있습니다. 
- 기능 업데이트. 아래 추가 참고를 참조하세요.


### <a name="feature-updates"></a>기능 업데이트

품질 및 지연할 수 없는 업데이트와 달리 Windows 10 "기능 업데이트"(주요 OS 릴리스)는 Microsoft에서 테스트하여 특정 업데이트 기능의 유효성을 검사한 후에만 Microsoft Teams 룸. Semi-Annual 채널(또는 테스트를 위해 해당 채널로 설정된 시스템이 있는 경우 대상 지정)에 릴리스되거나 자체 시도 또는 구성에 의해 수동으로 푸시된 경우에도 끝에 있는 블록이 제거될 때까지 설치를 허용하지 않습니다.

Microsoft Teams "첫 실행"을(를) 사용하여 Windows 업데이트로 Windows 장치를 자동으로 설치하거나 다시 시작하지 Windows 않습니다. 그러나 시스템에서 업데이트를 다운로드하고 다음 재부팅이 설치될 때까지 기다릴 수 있습니다. 누군가가 수동으로 다시 시작하지 않는 한 자동 야간 재부팅 시 설치가 수행됩니다. Windows 업데이트가 대화방에서 투명해야 한다고 하여 UI가 업데이트에 의해 중단되지 Windows 합니다.

도메인 가입을 선택한 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용하며, 장치가 업데이트를 설치하거나 업무 시간 동안 다시 부과될 수 있는 정책 또는 작업에 특히 주의하세요. UI를 통해 업데이트에 대해 알리거나 사용 중에 배포를 다시 Windows 시스템이 있는 경우 구성을 살펴보는 것이 좋습니다.