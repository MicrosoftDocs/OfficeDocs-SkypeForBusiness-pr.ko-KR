---
title: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
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
description: 관리자는 Microsoft 팀 대화방에 대 한 windows 업데이트 및 Windows 기능 업데이트를 관리 하는 방법을 알아볼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e52c1fdf3bb35be6869320aa57e6f5aff5fd0773
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905310"
---
# <a name="manage-windows-updates"></a>Windows 업데이트 관리

Microsoft 팀 대화방은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise (VL)에서 실행 되며 표준 데스크톱 컴퓨터로 동일한 Windows 업데이트 및 OS 빌드를 받습니다.

Windows 업데이트는 다음 섹션에서 설명 하는 대로 관리할 수 있습니다.

## <a name="hands-off-approach"></a>실습 방법 

- 기본적으로 업데이트는 Windows 업데이트에서 직접 자동으로 다운로드 되 고 시간이 지난 후에 설치 됩니다.
- 비 지연 업데이트 설치 일-자동으로 릴리스 중 하나입니다.
- 품질 업데이트 및 드라이버는 자동으로 일을 다운로드 하 고 설치 합니다.
- 기능 업데이트. 팔 로우 하는 노트를 참조 하세요.

## <a name="windows-updates-for-business-gpo-or-intune"></a>비즈니스용 Windows 업데이트 (GPO 또는 Intune)  

- [비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 다운로드
- 업데이트는 Windows Update 또는 WSUS에서 다운로드 되지만 원래 릴리스 날짜 이후에는 구성 지연 됩니다.
- 여러 Ou 또는 필터링 된 정책을 사용 하 여 관리자가 품질 업데이트를 먼저 설치 하 고 나중에 설치할 장치를 지정할 수 있는 배포 "링"을 만들 수 있습니다. 구성 관리자에서 Windows 업데이트를 관리 하는 오버 헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템 하위 집합에서 안정성 및 성능을 테스트할 수 있습니다.
- 대역폭 관리와 비즈니스용 Windows 업데이트 제어 기능을 둘 다 원할 경우 비즈니스용 WSUS 및 Windows 업데이트를 동시 [에 구성할](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) 수 있습니다.
- 기능 업데이트. 팔 로우 하는 노트를 참조 하세요.

## <a name="wsusconfiguration-manager"></a>WSUS/구성 관리자

- [WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) 다운로드
- 비즈니스를 위한 Windows 업데이트와 비슷하지만, 각 "링" 내에서 특정 KB의 대상을 지정 하는 추가 옵션 또는 전체 배포를 사용 하는 것과 매우 유사 합니다. 각 업데이트는 지연에 의존 하지 않고 각각 개별적으로 배포 하 고 테스트할 수 있습니다.
- 기능 업데이트. 팔 로우 하는 노트를 참조 하세요.

### <a name="feature-updates"></a>기능 업데이트

품질 및 지연 불가능 업데이트와 달리 Windows 10 "기능 업데이트" (주요 OS 릴리스)는 microsoft 테스트 후에만 설치 되며 Microsoft 팀 대화방에서 특정 업데이트 기능을 확인 하 고 유효성을 검사 합니다. 업데이트가 반기 채널 (또는 테스트를 위해 해당 채널에 설정 된 시스템을 사용 하는 경우) 또는 수동으로 푸시 된 경우에도 Microsoft Room 시스템 장치는 테스트 되지 않은 업데이트를 설치할 수 없습니다.

Microsoft 팀 대화방은 손을 끄는 방법으로 "부재 중"으로 작동 하며 windows 업데이트를 설치 하거나 windows 업데이트를 위해 자동으로 장치를 다시 부팅 하지 않습니다. 시스템은 업데이트를 다운로드 하 고 다음 번 다시 부팅 하 여 설치할 때까지 기다립니다. 다른 사용자가 수동으로 다시 부팅 하지 않는 한, 자동으로 야간 부팅 시에만 설치 됩니다. Windows 업데이트는 채팅방에서 투명 해야 하며 정상 작업은 Windows 업데이트에 의해 중단 되어서는 안 됩니다.

도메인 참가 장치를 선택 하는 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용 합니다. 비즈니스 시간에 장치 업데이트 또는 강제 재부팅을 발생 시키는 정책 또는 작업에 특히 주의를 기울여야 합니다. 배포에서 시스템을 사용 하는 동안 다시 부팅 하거나 UI를 통해 Windows 업데이트에 대 한 알림을 사용 중이 아니면 해당 동작이 발생 하는 경우 구성을 검토 합니다.