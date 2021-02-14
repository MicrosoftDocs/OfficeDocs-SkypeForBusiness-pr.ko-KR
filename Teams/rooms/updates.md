---
title: Microsoft Teams 회의실에 대한 Windows 업데이트 관리
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
description: 관리자는 Microsoft Teams 회의실에 대한 Windows 업데이트 및 Windows 기능 업데이트를 관리하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e52c1fdf3bb35be6869320aa57e6f5aff5fd0773
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905310"
---
# <a name="manage-windows-updates"></a>Windows 업데이트 관리

Microsoft Teams 회의실은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise(VL)에서 실행하며 표준 데스크톱 컴퓨터와 동일한 Windows 업데이트 및 OS 빌드를 수신합니다.

Windows 업데이트는 다음 섹션에서 설명한 따라 관리할 수 있습니다.

## <a name="hands-off-approach"></a>핸드오프 방법 

- 기본적으로 업데이트는 Windows 업데이트에서 자동으로 직접 다운로드되고 근무 시간 이하는 동안 설치됩니다.
- 지연이 없는 업데이트는 릴리스 1일차에 자동으로 설치됩니다.
- 품질 업데이트 및 드라이버는 자동으로 1일차를 다운로드하여 설치합니다.
- 기능 업데이트. 다음 노트를 참조합니다.

## <a name="windows-updates-for-business-gpo-or-intune"></a>비즈니스용 Windows 업데이트(GPO 또는 Intune)  

- [비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 다운로드
- 업데이트는 Windows 업데이트 또는 WSUS에서 다운로드되지만 원래 릴리스 날짜를 지난 구성된 지연으로 인해 다운로드됩니다.
- 여러 US 또는 필터링된 정책을 사용하여 관리자가 먼저 품질 업데이트를 설치하고 나중에 설치할 디바이스를 지정할 수 있는 배포 "링"을 만들 수 있습니다. 구성 관리자에서 Windows 업데이트를 관리하는 오버헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템의 하위 집합에서 안정성 및 성능을 테스트할 수 있습니다.
- 대역폭 관리와 비즈니스용 Windows [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) 업데이트에서 제공하는 제어를 모두 원하는 경우 WSUS 및 비즈니스용 Windows 업데이트를 동시에 구성할 수 있습니다.
- 기능 업데이트. 다음 노트를 참조합니다.

## <a name="wsusconfiguration-manager"></a>WSUS/구성 관리자

- [WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) 다운로드
- 비즈니스용 Windows 업데이트와 마찬가지로 각 "링" 또는 전체 배포 내에서 특정 KB를 대상으로 하는 추가 옵션도 있습니다. 각 업데이트는 지연에만 집중하지 않고 개별적으로 배포하고 테스트할 수 있습니다.
- 기능 업데이트. 다음 노트를 참조합니다.

### <a name="feature-updates"></a>기능 업데이트

품질 및 지연할 수 없는 업데이트와 달리 Windows 10 "기능 업데이트"(주요 OS 릴리스)는 Microsoft가 Microsoft Teams 회의실에서 특정 업데이트 기능을 테스트하고 유효성을 검사한 후에만 설치됩니다. 업데이트가 Semi-Annual 채널(또는 테스트용 채널로 설정된 시스템이 있는 경우 대상 지정)에 릴리스되거나 수동으로 푸시된 경우에도 Microsoft Room Systems 디바이스는 테스트되지 않은 업데이트를 설치할 수 없습니다.

Microsoft Teams 회의실은 실습 방식으로 "가능한" 기능을 수행하며 Windows 업데이트에 대해 Windows 업데이트를 설치하거나 장치를 자동으로 재부팅하지 않습니다. 시스템은 업데이트를 다운로드하고 다음 재부팅이 설치될 때까지 기다릴 수 있습니다. 누군가가 수동으로 재부팅하지 않는 한 자동 야간 재부팅 시에만 설치가 수행됩니다. Windows 업데이트는 방에서 투명해야 합니다. Windows 업데이트로 인해 정상적인 작업을 중단하지 말아야 합니다.

도메인 가입 디바이스를 선택하는 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용 합니다. 업무 시간 동안 디바이스 업데이트 또는 강제 재부팅이 수행되는 정책 또는 작업에 특히 주의하세요. 배포의 시스템은 사용 중에 재부팅되거나 사용 시간 동안 UI에 대한 Windows 업데이트에 대해 경고하지 말고 해당 동작이 발생하는 경우 구성을 검토합니다.