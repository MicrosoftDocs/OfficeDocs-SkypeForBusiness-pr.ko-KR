---
title: 장치 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가 하면 비즈니스용 Skype Server 제어판의 테스트 장치 페이지에 있는 목록에 표시 됩니다.
ms.openlocfilehash: 223efaf8a72c5ea0b7922a28b1dc26a6395e43ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196341"
---
# <a name="test-device"></a>장치 테스트

테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가 하면 비즈니스용 Skype Server 제어판의 **테스트 장치** 페이지에 있는 목록에 표시 됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**테스트 장치** 페이지에서 다음 작업을 수행할 수 있습니다.

- 전역 또는 특정 사이트에 대 한 테스트 장치를 추가 합니다.

- 기존 테스트 장치에 대 한 옵션을 수정 합니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.

- **새로운** 다음 범위를 사용 하 여 새 테스트 장치를 추가할 수 있습니다.

  - 전역

  - 사이트

- **편집** 목록에서 테스트 장치의 옵션을 변경할 수 있습니다. 이 옵션을 사용 하 여 다음을 수행할 수 있습니다.

  - **세부 정보 표시** 이 옵션은 테스트 장치에 대 한 옵션을 변경할 수 있는 대화 상자를 엽니다.

  - **모두 선택** 이 옵션은 목록의 모든 테스트 장치를 선택 합니다.

  - **삭제** 이 옵션은 선택한 모든 테스트 장치를 삭제 합니다.

- **새로 고침** 테스트 장치 목록을 새로 고쳐 모든 테스트 장치에 대 한 옵션의 상태를 확인할 수 있습니다.

장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서의 [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)를 참조하세요.
## <a name="see-also"></a>참고 항목

[테스트 장치: 새로 만들기 또는 기존 항목 편집](test-device-create-new-or-edit-existing.md)

[신규-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[조직의 디바이스에 대 한 소프트웨어 업데이트 보기](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
