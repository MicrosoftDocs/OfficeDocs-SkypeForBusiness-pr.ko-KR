---
title: Microsoft Teams 룸 대한 Windows 업데이트 관리
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: ''
description: 관리 Microsoft Teams 룸 대한 Windows 업데이트 및 Windows 기능 업데이트를 관리하는 방법에 대해 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1df5521bdfafe38854a0b6a3821e86218ce95a0b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272183"
---
# <a name="manage-windows-updates"></a>Windows 업데이트 관리

Microsoft Teams 룸 Windows 10 Enterprise IoT 또는 VL(Windows 10 Enterprise)에서 실행되며 표준 데스크톱 컴퓨터와 동일한 Windows 업데이트 및 OS 빌드를 받습니다.

Windows 업데이트 다음 섹션에서 설명한 대로 관리할 수 있습니다.

## <a name="hands-off-approach"></a>실습 접근 방식 

- 기본적으로 업데이트는 Windows 업데이트 직접 다운로드되고 작업 시간 쉬는 시간에 자동으로 설치됩니다.
- 지연할 수 없는 업데이트 릴리스 1일째에 자동으로 설치됩니다.
- 품질 업데이트 드라이버가 1일차를 자동으로 다운로드하여 설치합니다.
- 기능 업데이트. 다음 노트를 참조하세요.

## <a name="windows-updates-for-business-gpo-or-intune"></a>비즈니스용 Windows 업데이트(GPO 또는 Intune)  

- [비즈니스용 Windows 업데이트](/windows/deployment/update/waas-manage-updates-wufb) 다운로드
- 업데이트 Windows 업데이트 또는 WSUS(Windows Server Update Services)에서 다운로드되지만 원래 릴리스 날짜를 지나서 구성된 지연이 있습니다.
- 여러 OU 또는 필터링된 정책을 사용하여 관리자가 품질 업데이트 먼저 설치하는 Teams 룸 디바이스와 나중에 설치할 디바이스를 지정할 수 있는 배포 "링"을 만들 수 있습니다. 안정성 및 성능은 Configuration Manager Windows 업데이트 관리하는 오버헤드 없이 전체 배포에서 업데이트를 배포하기 전에 디바이스의 하위 집합에서 테스트할 수 있습니다.
- 대역폭 관리와 비즈니스용 Windows 업데이트 제공하는 제어를 모두 원하는 경우 WSUS 및 비즈니스용 Windows 업데이트 [동시에 구성할](/windows/deployment/update/waas-integrate-wufb) 수 있습니다.
- 기능 업데이트. 다음 노트를 참조하세요.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) 다운로드
- 비즈니스용 Windows 업데이트 마찬가지로 각 "링" 또는 전체 배포 내에서 특정 KB를 대상으로 하는 추가 옵션이 있습니다. 각 업데이트는 지연에만 의존하지 않고 개별적으로 배포하고 테스트할 수 있습니다.
- 기능 업데이트. 다음 노트를 참조하세요.

### <a name="feature-updates"></a>기능 업데이트

품질 및 지연 불가능한 업데이트와 달리 Windows 10 "기능 업데이트"(주요 OS 릴리스)은 Microsoft가 Microsoft Teams 룸 사용하여 지정된 업데이트 기능을 테스트하고 유효성을 검사한 후에만 설치됩니다. 업데이트가 Semi-Annual 채널(또는 테스트를 위해 해당 채널로 설정된 경우 대상 지정됨)으로 릴리스되거나 수동으로 푸시되더라도 Microsoft Teams 룸 테스트되지 않은 업데이트를 설치할 수 없습니다.

Microsoft Teams 룸 실습 접근 방식을 사용하여 "기본 제공" 기능을 수행합니다. Teams 룸 업데이트를 다운로드하고 다음 재부팅이 설치되기를 기다립니다. 누군가가 수동으로 다시 부팅하지 않는 한, 설치는 자동 야간 재부팅에서만 발생합니다. Windows 업데이트 회의실에서 투명해야 하며 Windows 업데이트 정상적인 작업을 중단해서는 안 됩니다.

도메인 가입 디바이스를 선택하는 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용할 수 있습니다. 업무 시간 동안 디바이스 업데이트 또는 강제 재부팅을 초래하는 정책 또는 작업에 특히 주의하세요. Teams 룸 사용 중에 다시 부팅하거나 사용 시간 동안 UI를 통해 Windows 업데이트 대해 경고하면 안 됩니다. 해당 동작이 발생하는 경우 구성을 검토합니다.
