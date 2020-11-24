---
title: 테 넌 트 업로드 및 통화 품질 대시보드에서 데이터 빌드 (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 테 넌 트를 업로드 하 고 CQD (통화 품질 대시보드에서) 데이터를 작성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 1ee722e63a8699e1447ffc0c2bc859a6a080d220
ms.sourcegitcommit: bac9aa29074ef32387dc05b3918e87d4c38d195d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385635"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="a029f-103">테 넌 트 업로드 및 통화 품질 대시보드에서 데이터 빌드 (CQD)</span><span class="sxs-lookup"><span data-stu-id="a029f-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="a029f-104">CQD (통화 품질 대시보드)를 최대한 활용 하려면 테 넌 트를 업로드 하 고 데이터를 작성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="a029f-105">테 넌 트 데이터 파일에는 두 가지 유형이 있습니다 ( [빌드](#upload-building-data-file) 및 [끝점](#endpoint-data-file)).</span><span class="sxs-lookup"><span data-stu-id="a029f-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="a029f-106">[여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)에 샘플 테 넌 트 데이터 서식 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="a029f-107">지도 작성에 대 한 도움말을 보려면 [CQD에 대 한 건물 지도 만들기](CQD-building-mapping.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a029f-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="a029f-108">Cqd 요약 보고서 대시보드의 CQD **설정** 메뉴에서 **테 넌 트 데이터 업로드** (cqd 맨 위에 있는 기어 아이콘)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="a029f-109">여기에서 관리자는 IP 주소와 지리 정보 매핑, 각 무선 액세스 지점 및 MAC 주소 매핑 등 조직의 빌드 및 끝점 정보를 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="a029f-110">팀 관리 센터 또는에서 CQD를 연 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 다음 오른쪽 위 모서리에 있는 기어 아이콘을 선택 하 고 **요약 보고서** 페이지에서 **테 넌 트 데이터 업로드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![데이터를 업로드 하는 동안 표시 되는 대화 상자 스크린샷](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="a029f-112">또는 처음으로 CQD를 방문 하는 경우에는 데이터를 업로드 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="a029f-113">**지금 업로드** 를 선택 하 여 **테 넌 트 데이터 업로드** 페이지로 신속 하 게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![데이터 작성을 업로드 하도록 사용자에 게 알리는 배너 스크린샷](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="a029f-115">**테 넌 트 데이터 업로드** 페이지에서 **찾아보기를** 선택 하 여 데이터 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="a029f-116">데이터 파일을 선택한 후 **시작 날짜** 를 지정 하 고 필요에 따라 끝 날짜를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="a029f-117">**시작 날짜** 를 선택한 후 **업로드** 를 선택 하 여 파일을 cqd에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="a029f-118">파일을 업로드 하기 전에 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="a029f-119">유효성 검사에 실패 하면 파일을 수정 하 라는 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="a029f-120">다음 그림에서는 데이터 파일의 열 수가 올바르지 않은 경우 발생 하는 오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![건물 데이터 업로드 오류를 표시 하는 대화 상자 예](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="a029f-122">유효성 검사 중에 오류가 발생 하지 않으면 파일 업로드가 성공적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="a029f-123">그런 다음 업로드 된 데이터 파일을 해당 페이지의 맨 아래에 있는 현재 테 넌 트에 대해 업로드 된 모든 파일의 전체 목록을 보여 주는 **My 업로드** 테이블에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="a029f-124">문서 파일 처리를 완료 하는 데 최대 4 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="a029f-125">이미 빌드 파일을 업로드 한 경우 누락 되거나 제외 된 서브넷을 추가 해야 하는 경우 새 서브넷을 추가 하 여 원본 파일을 수정한 다음 현재 파일을 제거 하 고 새로 편집한 파일을 다시 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="a029f-126">CQD에는 하나의 활성 빌드 데이터 파일만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="a029f-127">빌드 데이터 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="a029f-127">Upload building data file</span></span>

<span data-ttu-id="a029f-128">CQD에 있는 테 넌 트 데이터 파일의 첫 번째 유형은 **빌드** 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="a029f-129">서브넷 열은 네트워크 + NetworkRange 열을 확장 한 다음 서브넷 열을 호출 레코드의 첫 번째 서브넷 또는 두 번째 서브넷 열에 조인 하 여 건물, 도시, 국가 또는 지역 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="a029f-130">업로드 하기 전에 유효성 검사를 통과 하려면 업로드 하는 데이터 파일의 형식이 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="a029f-131">파일은 tsv 파일 (열은 탭으로 구분) 또는 .csv 파일 (열은 쉼표로 구분) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="a029f-132">데이터 파일에 표 머리글 행이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="a029f-133">데이터 파일의 첫 줄은 "네트워크"와 같은 머리글 레이블이 아닌 실제 데이터 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="a029f-134">파일의 데이터 형식은 문자열, 정수 또는 부울 일 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="a029f-135">Integer 데이터 형식의 경우 값은 숫자 값 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="a029f-136">부울 값은 0 또는 1 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="a029f-137">열에 문자열 데이터 형식이 사용 되는 경우 데이터 필드는 비어 있을 수 있지만 여전히 탭 또는 쉼표로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="a029f-138">빈 데이터 필드는 빈 문자열 값만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="a029f-139">각 행에는 15 개의 열이 있고, 각 열에는 적절 한 데이터 형식이 있어야 하며, 열은 다음 표에 나열 된 순서 (쉼표 또는 탭으로 구분)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-139">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="a029f-140">**데이터 파일 형식 빌드**</span><span class="sxs-lookup"><span data-stu-id="a029f-140">**Building data file format**</span></span>
  
  | <span data-ttu-id="a029f-141">열 이름</span><span class="sxs-lookup"><span data-stu-id="a029f-141">Column name</span></span>        | <span data-ttu-id="a029f-142">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a029f-142">Data type</span></span> | <span data-ttu-id="a029f-143">예제</span><span class="sxs-lookup"><span data-stu-id="a029f-143">Example</span></span>                   | <span data-ttu-id="a029f-144">지침</span><span class="sxs-lookup"><span data-stu-id="a029f-144">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="a029f-145">네트워크 Ip</span><span class="sxs-lookup"><span data-stu-id="a029f-145">NetworkIP</span></span>          | <span data-ttu-id="a029f-146">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-146">String</span></span>    | <span data-ttu-id="a029f-147">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a029f-147">192.168.1.0</span></span>               | <span data-ttu-id="a029f-148">필수</span><span class="sxs-lookup"><span data-stu-id="a029f-148">Required</span></span>              |
  | <span data-ttu-id="a029f-149">NetworkName</span><span class="sxs-lookup"><span data-stu-id="a029f-149">NetworkName</span></span>        | <span data-ttu-id="a029f-150">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-150">String</span></span>    | <span data-ttu-id="a029f-151">미국/시애틀/시애틀-해상-1</span><span class="sxs-lookup"><span data-stu-id="a029f-151">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="a029f-152">필수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a029f-152">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="a029f-153">네트워크 범위</span><span class="sxs-lookup"><span data-stu-id="a029f-153">NetworkRange</span></span>       | <span data-ttu-id="a029f-154">숫자로</span><span class="sxs-lookup"><span data-stu-id="a029f-154">Number</span></span>    | <span data-ttu-id="a029f-155">kbps</span><span class="sxs-lookup"><span data-stu-id="a029f-155">26</span></span>                        | <span data-ttu-id="a029f-156">필수</span><span class="sxs-lookup"><span data-stu-id="a029f-156">Required</span></span>              |
  | <span data-ttu-id="a029f-157">BuildingName</span><span class="sxs-lookup"><span data-stu-id="a029f-157">BuildingName</span></span>       | <span data-ttu-id="a029f-158">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-158">String</span></span>    | <span data-ttu-id="a029f-159">시애틀-해상-1</span><span class="sxs-lookup"><span data-stu-id="a029f-159">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="a029f-160">필수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a029f-160">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="a029f-161">소유자 배송 유형</span><span class="sxs-lookup"><span data-stu-id="a029f-161">OwnershipType</span></span>      | <span data-ttu-id="a029f-162">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-162">String</span></span>    | <span data-ttu-id="a029f-163">Contoso.com</span><span class="sxs-lookup"><span data-stu-id="a029f-163">Contoso</span></span>                   | <span data-ttu-id="a029f-164">선택</span><span class="sxs-lookup"><span data-stu-id="a029f-164">Optional</span></span>              |
  | <span data-ttu-id="a029f-165">BuildingType</span><span class="sxs-lookup"><span data-stu-id="a029f-165">BuildingType</span></span>       | <span data-ttu-id="a029f-166">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-166">String</span></span>    | <span data-ttu-id="a029f-167">IT 종료</span><span class="sxs-lookup"><span data-stu-id="a029f-167">IT Termination</span></span>            | <span data-ttu-id="a029f-168">선택</span><span class="sxs-lookup"><span data-stu-id="a029f-168">Optional</span></span>              |
  | <span data-ttu-id="a029f-169">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="a029f-169">BuildingOfficeType</span></span> | <span data-ttu-id="a029f-170">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-170">String</span></span>    | <span data-ttu-id="a029f-171">공정</span><span class="sxs-lookup"><span data-stu-id="a029f-171">Engineering</span></span>               | <span data-ttu-id="a029f-172">선택</span><span class="sxs-lookup"><span data-stu-id="a029f-172">Optional</span></span>              |
  | <span data-ttu-id="a029f-173">곳</span><span class="sxs-lookup"><span data-stu-id="a029f-173">City</span></span>               | <span data-ttu-id="a029f-174">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-174">String</span></span>    | <span data-ttu-id="a029f-175">시애틀</span><span class="sxs-lookup"><span data-stu-id="a029f-175">Seattle</span></span>                   | <span data-ttu-id="a029f-176">권장</span><span class="sxs-lookup"><span data-stu-id="a029f-176">Recommended</span></span>           |
  | <span data-ttu-id="a029f-177">ZipCode</span><span class="sxs-lookup"><span data-stu-id="a029f-177">ZipCode</span></span>            | <span data-ttu-id="a029f-178">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-178">String</span></span>    | <span data-ttu-id="a029f-179">98001</span><span class="sxs-lookup"><span data-stu-id="a029f-179">98001</span></span>                     | <span data-ttu-id="a029f-180">권장</span><span class="sxs-lookup"><span data-stu-id="a029f-180">Recommended</span></span>           |
  | <span data-ttu-id="a029f-181">명칭</span><span class="sxs-lookup"><span data-stu-id="a029f-181">Country</span></span>            | <span data-ttu-id="a029f-182">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-182">String</span></span>    | <span data-ttu-id="a029f-183">보세요</span><span class="sxs-lookup"><span data-stu-id="a029f-183">US</span></span>                        | <span data-ttu-id="a029f-184">권장</span><span class="sxs-lookup"><span data-stu-id="a029f-184">Recommended</span></span>           |
  | <span data-ttu-id="a029f-185">상태</span><span class="sxs-lookup"><span data-stu-id="a029f-185">State</span></span>              | <span data-ttu-id="a029f-186">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-186">String</span></span>    | <span data-ttu-id="a029f-187">WA</span><span class="sxs-lookup"><span data-stu-id="a029f-187">WA</span></span>                        | <span data-ttu-id="a029f-188">권장</span><span class="sxs-lookup"><span data-stu-id="a029f-188">Recommended</span></span>           |
  | <span data-ttu-id="a029f-189">영역인</span><span class="sxs-lookup"><span data-stu-id="a029f-189">Region</span></span>             | <span data-ttu-id="a029f-190">문자열</span><span class="sxs-lookup"><span data-stu-id="a029f-190">String</span></span>    | <span data-ttu-id="a029f-191">MSUS</span><span class="sxs-lookup"><span data-stu-id="a029f-191">MSUS</span></span>                      | <span data-ttu-id="a029f-192">권장</span><span class="sxs-lookup"><span data-stu-id="a029f-192">Recommended</span></span>           |
  | <span data-ttu-id="a029f-193">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a029f-193">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="a029f-194">부울</span><span class="sxs-lookup"><span data-stu-id="a029f-194">Bool</span></span>      | <span data-ttu-id="a029f-195">1</span><span class="sxs-lookup"><span data-stu-id="a029f-195">1</span></span>             | <span data-ttu-id="a029f-196">필수</span><span class="sxs-lookup"><span data-stu-id="a029f-196">Required</span></span>              |
  | <span data-ttu-id="a029f-197">Express 경로<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a029f-197">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="a029f-198">부울</span><span class="sxs-lookup"><span data-stu-id="a029f-198">Bool</span></span>      | <span data-ttu-id="a029f-199">0</span><span class="sxs-lookup"><span data-stu-id="a029f-199">0</span></span>             | <span data-ttu-id="a029f-200">필수</span><span class="sxs-lookup"><span data-stu-id="a029f-200">Required</span></span>              |
  | <span data-ttu-id="a029f-201">VPN</span><span class="sxs-lookup"><span data-stu-id="a029f-201">VPN</span></span>                | <span data-ttu-id="a029f-202">부울</span><span class="sxs-lookup"><span data-stu-id="a029f-202">Bool</span></span>      | <span data-ttu-id="a029f-203">0</span><span class="sxs-lookup"><span data-stu-id="a029f-203">0</span></span>                         | <span data-ttu-id="a029f-204">선택</span><span class="sxs-lookup"><span data-stu-id="a029f-204">Optional</span></span>              |

  <span data-ttu-id="a029f-205"><sup>1</sup> CQD에는 필요 하지 않지만, 템플릿은 빌드 및 네트워크 이름을 표시 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-205"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="a029f-206"><sup>2</sup> 이 설정을 사용 하 여 서브넷이 회사 네트워크 내에 있는지 여부를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-206"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="a029f-207">용도를 다른 용도로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-207">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="a029f-208"><sup>3</sup> 이 설정을 사용 하 여 네트워크에서 Azure express를 사용 하는지 여부를 반영할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-208"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="a029f-209">용도를 다른 용도로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-209">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="a029f-210">**예제 행:**</span><span class="sxs-lookup"><span data-stu-id="a029f-210">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="a029f-211">네트워크 범위를 사용 하 여 수퍼 네트 (단일 라우팅 접두사가 있는 여러 서브넷의 조합)를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-211">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="a029f-212">모든 새 건물 업로드가 겹치는 범위에 대해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-212">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="a029f-213">문서 파일을 이전에 업로드 한 경우에는 현재 파일을 다운로드 한 후 다시 업로드 하 여 겹치는 내용을 식별 하 고 문제를 해결 한 후 다시 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-213">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="a029f-214">이전에 업로드 한 파일의 겹치기로 인해 보고서의 건물에 대해 잘못 된 서브넷 매핑이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-214">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="a029f-215">특정 VPN 구현에서는 서브넷 정보가 정확 하 게 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-215">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="a029f-216">VPN 열은 선택 사항이 며 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-216">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="a029f-217">VPN 열의 값이 1로 설정 되 면 해당 행이 표시 하는 서브넷이 서브넷 내의 모든 IP 주소와 일치 하도록 완전히 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-217">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="a029f-218">이러한 서브넷을 완전히 확장 하면 데이터 작성이 포함 된 쿼리에 대 한 쿼리 시간에 부정적인 영향을 주므로이를 사용 하 여 VPN 서브넷에 대해서만이 방법을 사용해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="a029f-218">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>


### <a name="supernetting"></a><span data-ttu-id="a029f-219">Supernetting</span><span class="sxs-lookup"><span data-stu-id="a029f-219">Supernetting</span></span>

<span data-ttu-id="a029f-220">각 서브넷을 정의 하는 대신, 일반적으로 클래스 없는 Inter-Domain Routing (CIDR) 이라고 하는 supernetting를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-220">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="a029f-221">*수퍼 네트* 는 단일 라우팅 접두사를 공유 하는 여러 서브넷의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-221">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="a029f-222">각 서브넷에 대 한 항목을 추가 하는 대신 수퍼 네트 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-222">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="a029f-223">Supernetting 지원 되지만이를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-223">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="a029f-224">예를 들어 Contoso의 마케팅 문서는 다음 서브넷으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-224">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="a029f-225">10.1.0.0/24-첫 번째 층</span><span class="sxs-lookup"><span data-stu-id="a029f-225">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="a029f-226">10.1.1.0/24-2 층</span><span class="sxs-lookup"><span data-stu-id="a029f-226">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="a029f-227">10.1.2.0/24-1/3 바닥</span><span class="sxs-lookup"><span data-stu-id="a029f-227">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="a029f-228">10.1.3.0/24-4 층</span><span class="sxs-lookup"><span data-stu-id="a029f-228">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="a029f-229">각 서브넷에 대 한 항목을 추가 하는 대신이 예제에서 10.1.0.0/22의 수퍼 네트 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-229">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="a029f-230">Network = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="a029f-230">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="a029f-231">네트워크 범위 = 22</span><span class="sxs-lookup"><span data-stu-id="a029f-231">Network Range = 22</span></span>

<span data-ttu-id="a029f-232">Supernetting를 구현 하기 전에 다음과 같은 몇 가지 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-232">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="a029f-233">Supernetting는 8 비트 ~ 28 비트 마스크로 서브넷 매핑에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-233">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="a029f-234">Supernetting는 시간을 덜 차지 하지만, 데이터의 다양성을 줄이는 비용을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-234">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="a029f-235">서브넷 10.1.2.0 관련 하 여 품질 문제가 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-235">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="a029f-236">Supernetting를 구현한 경우 서브넷이 있는 건물 위치 또는 네트워크 종류 (예: 랩)를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-236">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="a029f-237">건물 및 업로드 된 밑면 위치 정보에 대 한 모든 서브넷을 정의한 경우 해당 차이점을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-237">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="a029f-238">수퍼 네트 주소가 올바르며 원하지 않는 서브넷을 catch 하지 않도록 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-238">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="a029f-239">데이터에서 192.168.0.0을 찾는 것은 매우 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-239">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="a029f-240">대부분의 조직에서이는 사용자가 집에 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-240">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="a029f-241">다른 사용자의 경우이는 위성 사무실의 IP 주소 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-241">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="a029f-242">조직에이 구성을 사용 하는 사무실이 있는 경우에는 [공용 서브넷](quality-of-experience-review-guide.md#common-subnets)을 사용 하 여 홈 네트워크와 내부 네트워크가 구분 되기 어렵기 때문에 문서 파일에 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a029f-242">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a029f-243">네트워크 범위를 사용 하 여 수퍼 네트를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-243">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="a029f-244">모든 새 빌드 데이터 파일 업로드는 겹치는 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-244">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="a029f-245">이전에 문서 파일을 업로드 한 경우에는 현재 파일을 다운로드 한 후 다시 업로드 하 여 겹치는 내용을 확인 하 고 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-245">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="a029f-246">이전에 업로드 한 파일의 겹치기로 인해 보고서의 건물에 대해 잘못 된 서브넷 매핑이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-246">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="a029f-247">VPN</span><span class="sxs-lookup"><span data-stu-id="a029f-247">VPN</span></span>

<span data-ttu-id="a029f-248">클라이언트가 Microsoft 365 또는 Office 365로 보내는 (체감 품질) 데이터 (CQD 데이터의 원본)에는 VPN 플래그가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-248">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="a029f-249">CQD는 첫 번째 VPN 및 두번째 VPN 치수로이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-249">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="a029f-250">그러나이 플래그는 Windows에 대 한 VPN 공급 업체의 보고 기능을 사용 하므로, 등록 된 VPN 네트워크 어댑터가 원격 액세스 어댑터입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-250">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="a029f-251">모든 VPN 공급 업체가 원격 액세스 어댑터를 제대로 등록 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-251">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="a029f-252">이 때문에 기본 제공 VPN 쿼리 필터를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-252">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="a029f-253">VPN 서브넷을 정확 하 게 표시 하 고 식별 하기 위해 위에서 설명한 VPN 열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-253">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="a029f-254">보고서에서 쉽게 식별할 수 있도록 VPN 네트워크에 레이블을 지정 하는 것도 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-254">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="a029f-255">다음은 VPN 서브넷에 레이블을 지정 하는 방법에 대 한 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-255">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="a029f-256">VPN 서브넷에 대 한이 필드에 "VPN"을 입력 하 여 **네트워크 이름을** 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-256">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![네트워크 이름을 사용한 VPN을 보여주는 QCD 보고서 스크린샷](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="a029f-258">VPN 서브넷에 대 한이 필드에 "VPN"을 입력 하 여 **건물 이름을** 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-258">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![건물 이름을 사용한 VPN을 보여주는 QCD 보고서 스크린샷](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="a029f-260">기본 연결이 무선 인 경우 VPN 연결이 네트워크 연결 형식을 유선으로 misidentify 하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-260">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="a029f-261">VPN 연결을 통해 화질을 볼 때 연결 형식이 정확 하 게 식별 되었다고 가정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-261">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="a029f-262">끝점 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="a029f-262">Endpoint data file</span></span>

<span data-ttu-id="a029f-263">다른 유형의 CQD 테 넌 트 데이터 파일은 **끝점** 데이터 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-263">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="a029f-264">열 값은 호출 레코드의 첫 번째 클라이언트 끝점 이름 또는 두 번째 클라이언트 끝점 이름 열에서 끝점 만들기, 모델 또는 형식 정보를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-264">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="a029f-265">업로드 하기 전에 유효성 검사를 통과 하려면 업로드 하는 데이터 파일의 형식이 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-265">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="a029f-266">파일은 tsv 파일 (열은 탭으로 구분) 또는 .csv 파일 (열은 쉼표로 구분) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-266">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="a029f-267">데이터 파일의 내용에 표 머리글이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="a029f-268">데이터 파일의 첫 줄은 "EndpointName"와 같은 머리글 레이블이 아닌 실제 데이터 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-268">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="a029f-269">모든 일곱 개의 열에는 String 데이터 형식만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-269">All seven columns use the String data type only.</span></span> <span data-ttu-id="a029f-270">허용 되는 최대 길이는 64 자입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-270">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="a029f-271">데이터 필드는 비어 있을 수 있지만 여전히 탭 또는 쉼표로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-271">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="a029f-272">빈 데이터 필드는 빈 문자열 값만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-272">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="a029f-273">EndpointName는 고유 해야 하며, 그렇지 않으면 업로드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-273">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="a029f-274">중복 행이 있거나 같은 EndpointName를 사용 하는 두 행이 충돌 하는 경우에는 잘못 된 연결이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-274">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="a029f-275">EndpointLabel1, EndpointLabel2 및 EndpointLabel3는 사용자 지정이 가능한 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-275">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="a029f-276">"IT 부서가 2018 노트북" 또는 "자산 태그 5678"와 같은 빈 문자열 또는 값 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-276">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="a029f-277">각 행에 대해 일곱 개의 열이 있어야 하 고 열 순서는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-277">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="a029f-278">**필드 순서:**</span><span class="sxs-lookup"><span data-stu-id="a029f-278">**Field order:**</span></span>

  <span data-ttu-id="a029f-279">EndpointName, EndpointMake, Endpointmake, Endpointmake, EndpointLabel1, EndpointLabel2, EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="a029f-279">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="a029f-280">**예제 행:**</span><span class="sxs-lookup"><span data-stu-id="a029f-280">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`


## <a name="update-a-building-file"></a><span data-ttu-id="a029f-281">문서 파일 업데이트</span><span class="sxs-lookup"><span data-stu-id="a029f-281">Update a building file</span></span>

<span data-ttu-id="a029f-282">빌드 및 서브넷 정보를 수집 하는 동안에는 관리자가 새 서브넷과 해당 건물 정보를 추가 하는 시간에 따라 빌드 파일을 여러 번에 업로드 하는 경우가 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-282">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="a029f-283">이 문제가 발생 하면 문서 파일을 다시 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-283">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="a029f-284">이 프로세스는 다음 섹션에서 설명 하는 몇 가지 예외를 포함 하 여 이전 섹션의 초기 업로드와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-284">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="a029f-285">한 번에 하나의 빌드 파일만 활성화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-285">Only one building file can be active at a time.</span></span> <span data-ttu-id="a029f-286">여러 빌드 파일이 누적 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-286">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="a029f-287">Net new 서브넷 추가</span><span class="sxs-lookup"><span data-stu-id="a029f-287">Add net new subnets</span></span>

<span data-ttu-id="a029f-288">원래 네트워크 토폴로지에 속하지 않는 CQD에 net new 서브넷을 추가 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-288">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="a029f-289">Net new 서브넷을 추가 하려면 CQD의 **테 넌 트 데이터 업로드** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-289">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="a029f-290">최신 복사본이 아직 없는 경우 원본 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-290">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="a029f-291">CQD에서 현재 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-291">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="a029f-292">원본 문서 파일을 편집 하 고 net 새 서브넷을 확보 하기 전에 하루에 한 번 이상 발생 하는 끝 날짜를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-292">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="a029f-293">원본 빌드 파일에 net new 서브넷을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-293">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="a029f-294">새로 수정한 빌드 파일을 업로드 하 고 이전 문서 파일 종료 후 1 일 동안 시작 날짜를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-294">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="a029f-295">누락 된 서브넷 추가</span><span class="sxs-lookup"><span data-stu-id="a029f-295">Add missing subnets</span></span>

<span data-ttu-id="a029f-296">관리 네트워크에 대 한 빌드 정보를 업로드 한 후에는 모든 관리 네트워크에 빌드 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-296">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="a029f-297">그러나 항상이 경우에 해당 되는 것은 아닙니다. 일반적으로 일부 서브넷이 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-297">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="a029f-298">이러한 없는 네트워크를 찾으려면 CQD의 **환경 보고서** 페이지에서 **누락 된 서브넷 보고서** 를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="a029f-298">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="a029f-299">이렇게 하면 건물 데이터 파일에 정의 되지 않은 10 개 이상의 오디오 스트림이 있는 모든 서브넷이 표시 되 고 바깥쪽으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-299">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="a029f-300">이 목록에 관리 네트워크가 없는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-300">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="a029f-301">서브넷이 없는 경우 다음 절차를 사용 하 여 원본 문서 데이터 파일을 업데이트 하 고 CQD에 다시 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-301">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="a029f-302">CQD의 **테 넌 트 데이터 업로드** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-302">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="a029f-303">최신 복사본이 아직 없는 경우 원본 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-303">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="a029f-304">CQD에서 현재 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-304">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="a029f-305">원본 파일에 새 서브넷을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-305">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="a029f-306">문서 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-306">Upload the building file.</span></span> <span data-ttu-id="a029f-307">CQD가 기록 데이터를 처리 하기 위해서는 시작 날짜를 최소 8 개월 이상으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-307">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a029f-308">조직의 테 넌 트 데이터만 표시 하도록 보고서를 필터링 하려면이 보고서에 대 한 **두 번째 테** 넌 트 id에 대 한 쿼리 필터로 테 넌 트 id를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-308">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="a029f-309">그렇지 않으면 보고서에 페더레이션된 서브넷이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-309">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="a029f-310">이번 달에 대 한 월 연도 보고서 필터를 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-310">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="a029f-311">**편집** 을 선택 하 고 **월 연도** 보고서 필터를 조정 하 여 새 기본 달을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a029f-311">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a029f-312">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a029f-312">Related topics</span></span>

[<span data-ttu-id="a029f-313">CQD에 대 한 건물 지도 만들기</span><span class="sxs-lookup"><span data-stu-id="a029f-313">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="a029f-314">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="a029f-314">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="a029f-315">CQD 란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="a029f-315">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="a029f-316">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="a029f-316">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="a029f-317">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="a029f-317">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="a029f-318">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="a029f-318">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="a029f-319">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="a029f-319">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a029f-320">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="a029f-320">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a029f-321">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="a029f-321">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
