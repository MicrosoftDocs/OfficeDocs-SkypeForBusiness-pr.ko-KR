---
title: 장치 로그 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: 장치 업데이트 웹 서비스에서는 장치 업데이트 작업을 기록하는 로그 파일이 자동으로 만들어집니다. 조직의 데이터 관리 전략의 일부로 로그 데이터 캐시 크기, 로그 파일 크기 또는 로그 파일을 제거 하기 전에 보관 하는 시간에 대 한 임계값을 설정 하는 것이 좋습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다. 장치 업데이트 웹 서비스에서 로그 파일을 자동으로 삭제하지 않도록 하려면 필요에 따라 로그 파일을 수동으로 삭제할 수 있습니다. 로그 설정은 전역적으로 또는 사이트별로 변경할 수 있습니다.
ms.openlocfilehash: 7621a70ebfb8a2129e468ce38655dcc61bdbf420
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822901"
---
# <a name="device-log-configuration"></a>장치 로그 구성

장치 업데이트 웹 서비스에서는 장치 업데이트 작업을 기록하는 로그 파일이 자동으로 만들어집니다. 조직의 데이터 관리 전략의 일부로 로그 데이터 캐시 크기, 로그 파일 크기 또는 로그 파일을 제거 하기 전에 보관 하는 시간에 대 한 임계값을 설정 하는 것이 좋습니다. 조직의 요구 사항에 따라 이러한 설정을 변경할 수 있습니다. 장치 업데이트 웹 서비스에서 로그 파일을 자동으로 삭제하지 않도록 하려면 필요에 따라 로그 파일을 수동으로 삭제할 수 있습니다. 로그 설정은 전역적으로 또는 사이트별로 변경할 수 있습니다.

> [!NOTE]
> 장치 업데이트 웹 서비스에서 구성한 로그 파일 유지 기간(일)보다 오래된 로그 파일을 자동으로 삭제할 시간을 구성할 수도 있습니다(기본적으로 10일 이상 된 로그 파일이 자동으로 삭제됨). 비즈니스용 Skype Server 제어판을 사용 하 여이 설정을 수정할 수 없습니다. 대신 비즈니스용 Skype Server Management Shell을 사용 해야 합니다. 만료 된 로그 파일을 삭제 하는 데 걸리는 시간을 지정 하려면-LogCleanUpTimeOfDay 매개 변수를 사용 하 여 **CsDeviceUpdateConfiguration** cmdlet을 사용 합니다. 자세한 내용은 [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)을 참조 하세요.

> [!CAUTION]
> 파일을 삭제하면 파일 시스템에서 영구 제거됩니다. 따라서 파일을 삭제한 후 복구할 수 없습니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**장치 로그 구성** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 장치 로그 구성을 전역적으로 또는 특정 사이트나 풀에 대해 추가

- 기존 장치 로그 구성에 대한 옵션 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.

- **새로운** 다음 범위를 사용 하 여 새 장치 로그 구성을 추가할 수 있습니다.

  - 전역

  - 사이트

- **편집** 목록에서 장치 로그 구성의 옵션을 변경할 수 있습니다. 이 옵션을 사용 하 여 다음을 수행할 수 있습니다.

  - **세부 정보 표시** 이 옵션은 장치 로그 구성에 대 한 옵션을 변경할 수 있는 대화 상자를 엽니다.

  - **모두 선택** 이 옵션은 목록의 모든 장치 로그 구성을 선택 합니다.

  - **삭제** 이 옵션은 선택한 모든 장치 로그 구성을 삭제 합니다.

- **새로 고침** 장치 로그 구성 목록을 새로 고쳐서 모든 장치 로그 구성 옵션의 상태를 확인할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
