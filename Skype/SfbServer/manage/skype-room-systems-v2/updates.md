---
title: Microsoft Teams 룸에 대한 Windows 업데이트 관리
ms.author: v-cichur
author: cichur
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams 룸에 대한 Windows 업데이트 관리
ms.openlocfilehash: 4f7fd6d49c78b229a3909e88689423dc95ce2c48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832878"
---
# <a name="manage-windows-updates"></a>Windows 업데이트 관리

Microsoft Teams 룸은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise(VL)에서 실행되는 표준 데스크톱과 동일한 Windows 업데이트 및 OS 빌드를 수신합니다.

Windows 업데이트는 다음과 같은 몇 가지 방법으로 관리할 수 있습니다.

## <a name="hands-off-approach"></a>핸드오프 방식 
- 업데이트는 Windows 업데이트에서 자동으로 직접 다운로드하고 시간 이적 시간 동안 설치할 수 있습니다. 구성을 변경하지 않았다면 이 상태가 기본 상태입니다.
- 지연되지 않는 업데이트는 첫날 릴리스를 자동으로 설치합니다. 
- 품질 업데이트 및 드라이버는 자동으로 1일을 다운로드하여 설치합니다. 
- 기능 업데이트 아래 추가 참고를 참조하세요. 

## <a name="windows-updates-for-business-gpo-or-intune"></a>[비즈니스용 Windows](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 업데이트(GPO 또는 Intune)   
- 업데이트는 WU 또는 WSUS에서 다운로드되지만 KB의 원래 릴리스 날짜를 지난 구성된 지연으로 다운로드됩니다. 
- 여러 OU 또는 필터링된 정책과 결합되어 배포 "링"을 만들 수 있습니다. 여기서 관리자는 먼저 품질 업데이트를 설치하는 장치와 나중에 설치할 장치를 지정할 수 있습니다. 이렇게 하면 Microsoft Endpoint Configuration Manager에서 Windows 업데이트를 관리하는 오버헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템의 하위 집합에서 안정성 및 성능 테스트를 할 수 있습니다.
- 대역폭 관리와 비즈니스용 Windows [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) 업데이트에서 제공하는 제어를 원하는 경우 WSUS 및 비즈니스용 Windows 업데이트를 동시에 구성할 수 있습니다.
- 기능 업데이트. 아래 추가 참고를 참조하세요.

## <a name="wsusconfiguration-manager"></a>[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- 비즈니스용 Windows 업데이트와 마찬가지로, 각 "링" 또는 전체 배포 내에서 특정 KB를 대상으로 지정하는 추가 옵션도 있습니다. 각 업데이트는 지연에만 사용되지 않고 개별적으로 배포 및 테스트할 수 있습니다. 
- 기능 업데이트. 아래 추가 참고를 참조하세요.


### <a name="feature-updates"></a>기능 업데이트

품질 및 지연할 수 없는 업데이트와 달리 Windows 10 "기능 업데이트"(주요 OS 릴리스)는 Microsoft Teams 룸에서 특정 업데이트 기능을 테스트하고 유효성을 검사한 후에만 설치됩니다. Semi-Annual 채널(또는 테스트를 위해 해당 채널로 설정된 시스템이 있는 경우 대상 지정)에 릴리스되거나 직접 시도 또는 구성에 의해 수동으로 푸시된 경우에도 마지막에 있는 블록이 제거될 때까지 설치를 허용하지 않습니다.

Microsoft Teams 룸 "첫 실행" 접근 방식을 사용하여 Windows 업데이트로 Windows 업데이트를 설치하거나 장치를 자동으로 다시 시작하지 않습니다. 그러나 시스템에서 업데이트를 다운로드하고 다음에 다시 시작하여 설치할 때까지 기다릴 수 있습니다. 누군가가 수동으로 다시 시작하지 않는 한 자동 야간 재부팅 시 설치가 수행됩니다. Windows 업데이트는 대화방에서 투명해야 합니다. WINDOWS 업데이트에 의해 UI가 중단되지 않습니다.

도메인에 가입하도록 선택한 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용하며, 장치가 업데이트를 설치하거나 업무 시간 동안 다시 시작하도록 할 수 있는 정책 또는 작업에 특히 주의하세요. UI를 통해 Windows 업데이트를 사용하거나 경고하는 동안 배포 재부팅에 시스템이 있는 경우 구성을 살펴보는 것이 좋습니다.
