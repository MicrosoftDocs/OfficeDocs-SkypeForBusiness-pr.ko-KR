---
title: Microsoft Teams Rooms용 Windows 업데이트 관리
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 관리자는 Microsoft Teams Rooms에 대한 Windows 업데이트 및 Windows 기능 업데이트를 관리하는 방법에 대해 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117366"
---
# <a name="manage-windows-updates"></a>Windows 업데이트 관리

Microsoft Teams Rooms는 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise(VL)에서 실행하며 표준 데스크톱 컴퓨터와 동일한 Windows 업데이트 및 OS 빌드를 수신합니다.

Windows 업데이트는 다음 섹션에서 설명한 따라 관리할 수 있습니다.

## <a name="hands-off-approach"></a>손 끄기 접근 방식 

- 기본적으로 업데이트는 Windows 업데이트에서 자동으로 직접 다운로드되고 근무 시간 동안 설치됩니다.
- 지연할 수 없는 업데이트는 일차 릴리스를 자동으로 설치합니다.
- 품질 업데이트 및 드라이버는 자동으로 일-1을 다운로드하고 설치합니다.
- 기능 업데이트. 다음 노트를 참조합니다.

## <a name="windows-updates-for-business-gpo-or-intune"></a>비즈니스용 Windows 업데이트(GPO 또는 Intune)  

- [비즈니스용 Windows 업데이트](/windows/deployment/update/waas-manage-updates-wufb) 다운로드
- 업데이트는 Windows 업데이트 또는 WSUS에서 다운로드되지만 원래 릴리스 날짜를 지난 구성된 지연으로 다운로드됩니다.
- 여러 US 또는 필터링된 정책을 사용하여 관리자가 먼저 품질 업데이트를 설치하고 나중에 설치할 디바이스를 지정할 수 있는 배포 "링"을 만들 수 있습니다. 구성 관리자에서 Windows 업데이트를 관리하는 오버헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템의 하위 집합에서 안정성 및 성능을 테스트할 수 있습니다.
- 비즈니스용 WSUS 및 Windows [](/windows/deployment/update/waas-integrate-wufb) 업데이트는 대역폭 관리와 비즈니스용 Windows 업데이트가 제공하는 제어 모두를 원하는 경우 동시에 구성할 수 있습니다.
- 기능 업데이트. 다음 노트를 참조합니다.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [WSUS/Configuration Manager 다운로드](/windows/deployment/update/waas-manage-updates-configuration-manager)
- 비즈니스용 Windows 업데이트와 마찬가지로 각 "링" 또는 전체 배포 내에서 특정 KB를 대상으로 하는 추가 옵션도 있습니다. 각 업데이트는 지연에만 사용되지 않고 개별적으로 배포 및 테스트할 수 있습니다.
- 기능 업데이트. 다음 노트를 참조합니다.

### <a name="feature-updates"></a>기능 업데이트

품질 및 지연되지 않는 업데이트와 달리 Windows 10 "기능 업데이트"(주요 OS 릴리스)는 Microsoft Teams Rooms에서 특정 업데이트 기능을 테스트하고 유효성을 검사한 후에만 설치됩니다. 업데이트가 테스트용 Semi-Annual 채널로 릴리스되거나 해당 채널로 설정되어 있는 경우 대상이 지정되어 있는 경우에도 Microsoft Room Systems 디바이스에서 테스트되지 않은 업데이트를 설치할 수 없습니다.

Microsoft Teams Rooms는 핸즈오프 접근 방식과 함께 "사용 가능한"을 작동하며 Windows 업데이트에 대해 Windows 업데이트를 설치하거나 디바이스를 자동으로 다시부팅하지 않습니다. 시스템은 업데이트를 다운로드하고 다음 재부팅이 설치될 때까지 기다렸다. 누군가가 수동으로 재부팅하지 않는 한, 설치는 자동 야간 재부팅에서만 발생합니다. Windows 업데이트는 룸에서 투명해야 합니다. Windows 업데이트로 정상적인 작업을 중단하면 안 됩니다.

도메인 조인 디바이스를 선택하는 경우 Microsoft 엔드포인트 구성 관리자 또는 WSUS를 사용 합니다. 업무 시간 동안 디바이스 업데이트 또는 강제 재부팅이 수행되는 정책 또는 작업에 특별한 주의를 기울입니다. 배포의 시스템은 사용 중에 다시 부팅하거나 사용 시간 동안 UI를 통해 Windows 업데이트에 대해 경고하지 말고 해당 동작이 발생하는 경우 구성을 검토합니다.