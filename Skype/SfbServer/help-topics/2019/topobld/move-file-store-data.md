---
title: 파일 저장소 데이터를 새 파일 저장소로 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype 서버 배포에 대해 현재 파일 저장소로 사용 중인 파일 서버를 제거해야 하는 경우 또는 현재 파일 저장소를 사용할 수 없게 만드는 다른 변경을 해야 하는 경우 먼저 새 공유를 만들어야 합니다. 그런 다음 다음 단계를 수행해야 합니다.
ms.openlocfilehash: 58b42d267723d96163d276e5578d5b044c700b26
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853482"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a>파일 저장소 데이터를 새 파일 저장소로 비즈니스용 Skype 서버

비즈니스용 Skype 서버 배포에 대해 현재 파일 저장소로 사용 중인 파일 서버를 제거해야 하는 경우 또는 현재 파일 저장소를 사용할 수 없게 만드는 다른 변경을 해야 하는 경우 먼저 새 공유를 만들어야 합니다. 그런 다음 다음 단계를 수행해야 합니다.

1. 제거할 비즈니스용 Skype 서버 저장소를 사용하는 모든 서비스를 종료합니다.

2. 토폴로지 작성기에서 파일 저장소를 정의하고 변경 내용을 게시하여 배포에서 새 파일 저장소를 사용할 수 있도록 합니다.

3. 데이터를 새 파일 저장소로 이동하십시오.

4. 서버 또는 서비스를 다시 시작합니다.

5. 선택적으로 이전 파일 공유 및 파일 폴더를 제거합니다.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>하나의 파일 저장소에서 새 파일 저장소로 파일 저장소 데이터를 이동하려면

1. 관리 도구가 설치된 RTCUniversersalServerAdmins 또는 CsServerAdministrator 그룹의 구성원으로 컴퓨터에 비즈니스용 Skype 서버 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3. 왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.

4. 제거할 파일 저장소를 사용하는 Standard Edition, Director, Standard Edition 서버 및 프런트 엔드 풀에 대해 서버 또는 풀을 선택하고 작업을 클릭한 다음 모든 서비스 중지를 **클릭합니다.** 

5. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.

6. 토폴로지 작성기 시작:  **시작,** 모든 프로그램, 비즈니스용 Skype 서버, 토폴로지 작성기 비즈니스용 Skype 서버 **클릭합니다.**

7. 파일 저장소를 사용하는 서버 또는 풀을 선택하고 다음을 실행합니다.

8. 서버 또는 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집 을 클릭합니다.**

9. 속성 **편집의** **연결 아래의** **파일** 저장소에서 새로 추가를 **클릭합니다.**

10. 새 **파일 저장소** 정의의 파일 서버 **FQDN에서** 파일 서버의 FQDN(FQDN)을 입력합니다. 파일 **공유에서** 새 파일 공유의 폴더 이름을 입력한 다음 확인을 **클릭합니다.**

     > [!IMPORTANT]
     > 이 단계에서는 토폴로지 작성기에서 사용할 새 파일 저장소를 정의합니다. 각 서버에 대해 정의하는 것이 아니라 한 번만 정의합니다. 토폴로지를 게시하기 전에 정의된 파일 서버에서 정의된 파일 공유를 만들어야 합니다. 자세한 내용은 [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14))를 참조하십시오.

11. 파일 저장소를 사용하는 각 서버 또는 풀에 대해 다음을 실행합니다.

12. 서버 또는 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집 을 클릭합니다.**

13. 속성 **편집의** **연결 아래의** **파일** 저장소에서 새 파일 공유를 선택하고 확인을 **클릭합니다.**

14. 토폴로지 게시, 복제 상태 확인 및 비즈니스용 Skype 서버 배포 마법사를 실행합니다. 자세한 내용은 [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14))을 참조하십시오.

15. 명령 프롬프트 시작: **시작,** 실행을 **클릭한** 다음 명령 프롬프트를 cmd.exe.

16. 명령줄에 다음을 입력합니다.

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S 스위치는 파일, 폴더 및 하위디렉터를 복사합니다. /XF 스위치는 Meeting.Active라는 모든 파일을 건너뜁습니다. 현재 버전의 robocopy.exe에 /MT 스위치를 사용하면 다중 스레드를 사용하여 복사 속도를 크게 향상시켜 줍니다. /LOG 스위치의 경우 디렉터리 경로 및 로그 파일 이름을 파일 형식의 C:\Logfiles\log.txt. 이 스위치는 명명된 위치에 작업 로그 파일을 만듭니다.

17. 데이터 복사본이 완료되면 Lync Server 제어판에서 토폴로지, 상태를 **클릭합니다.**

18. 서비스를 중지한 각 서버 또는 풀에 대해 서버 또는 풀을 선택하고 작업을 **클릭한** 다음 모든 서비스 **시작을 클릭합니다.**

19. 토폴로지에서 오래된 파일 저장소를 제거한 후 토폴로지를 게시합니다. 자세한 내용은 [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))를 참조하십시오.

20. (선택 사항) 바로 전에 제거한 파일 저장소가 포함된 컴퓨터에 로컬 Administrators 그룹 또는 도메인 관리자 그룹의 구성원으로 로그온한 후 오래된 파일 공유 및 디렉터리를 제거합니다.

## <a name="see-also"></a>참고 항목

[서버를 다른 파일 저장소에 다시 할당](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[파일 저장소 제거](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))