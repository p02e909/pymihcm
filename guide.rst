Exercises
=========

Lớp học Python3, nếu máy bạn có cả 2 phiên bản, khi chạy lệnh ``python ...``
dùng ``python3`` thay vì ``python`` để tránh dùng nhầm Python2.

Hướng dẫn làm bài tập
---------------------

Tất cả bài tập phải làm vào trong thư mục ``exercises``, sửa nội dung của các file ``.py`` đã có tương ứng với bài tập cần làm.
Học xong chương 3 thì làm bài 'ex3_*.py' như ex3_1.py, ex3_2.py ...

Riêng ``ex35_*.py`` là bài làm thêm cho học viên từ buổi 3 đến
buổi 5. Khuyến khích dùng list comprehension.

Editor
^^^^^^

Cài đặt editor để mở code, xem tại `đây <https://gitlab.com/pyfml/prepare#c%C3%A0i-%C4%91%E1%BA%B7t-editor-sau-bu%E1%BB%95i-2->`_

Cách xử lý "lỗi"
^^^^^^^^^^^^^^^^

Khi chạy lệnh không thành công, vui lòng cung cấp đầy đủ câu lệnh và output,
không chỉ nói "lỗi". Trên Slack, viết code vào trong dấu ``` (dấu cạnh số 1
trên bàn phím) như sau::

  ```
  codehere
  ```

Nếu code quá dài, paste code vào đây https://glot.io/
lấy link để paste vào Slack channel.

Lấy code về máy
^^^^^^^^^^^^^^^^

Cài đặt git để quản lý các file code. Xem chi tiết tại https://gitlab.com/pyfml/prepare#chu%E1%BA%A9n-b%E1%BB%8B-tr%C6%B0%E1%BB%9Bc-bu%E1%BB%95i-3

Clone (download) repo của lớp học về máy nếu chưa clone::

  git clone https://gitlab.com/pyfml/pyfml.git pyfml

Các bước nộp bài
^^^^^^^^^^^^^^^^

**MỖI LẦN** làm bài tập, làm như sau:

Vào thư mục ``pyfml``, kiểm tra branch::

  cd pyfml # chuyển đến pyfml
  git branch

Kết quả::

  * master

Nếu không thấy kết quả có ``* master``, hãy chuyển sang branch master trước::

  git checkout master

Lấy phiên bản mới nhất của branch master từ GitLab về máy::

  git pull origin master

Tạo branch mới để nộp bài::

  git checkout -b pymi_XXYYZZ_YOURNAME_lesson

Ví dụ học viên khoá 1704 Hà Nội, tên HungNV, nộp bài 3::

  git checkout -b pymi_1704HN_hungnv_bai3

**Branch này sẽ chứa tất cả bài tập của bài học đó (ở ví dụ này là bài 3),
chỉ tạo duy nhất 1 branch cho một bài học**.

Sau đó làm bài tập và lưu vào git như sau:

Ví dụ bài 3.1 sẽ sửa file::

  ex3_1.py

bằng editor đã cài.

Nội dung của file này chứa đề bài và lời giải của bài toán.
Học viên sửa nội dung trong function solve() để trả về kết quả
phù hợp, đặt `result` bằng giá trị cần tìm. Không sửa đề bài, không sửa hàm
main, không return giá trị khác `result`.

Và chạy file này với lệnh::

  python ex3_1.py  # Trên Linux/Mac, gõ python3 để đảm bảo dùng đúng phiên bản.

Học viên cài và sử dụng
`flake8 <http://flake8.pycqa.org/en/latest/index.html#quickstart>`_
để kiểm tra code viết đúng chuẩn chưa (chỉ bắt buộc sau buổi 4)::

  flake8 ex3_1.py

Nếu thấy không in ra gì tức code đã đúng chuẩn Python (PEP8) rồi 🏆

Học viên chạy lệnh sau tại thư mục `pyfml` để kiểm tra xem bài làm mình đã đúng
chưa::

  python -m unittest discover -s tests -vvv

Nếu đúng, output sẽ trông như sau::

  test_ex3_0 (test_ex3.TestExercise3) ... ok

Nếu có exception xảy ra hay chưa làm, kết quả sẽ như sau::

  test_ex3_0 (test_ex3.TestExercise3) ... ERROR

Nếu sai, kết quả sẽ như sau::

  test_ex3_0 (test_ex3.TestExercise3) ... FAIL

Hãy đọc chi tiết của phần output sau khi chạy câu lệnh để xem lỗi/sai gì.
Không cần quan tâm đến các bài mình chưa học.

Làm bài xong học viên lưu vào git::

  git add ex3_1.py
  git commit -m 'add'

Push (đẩy) bài tập lên trang GitLab::

  git push origin YOUR_BRANCH  # CHÚ Ý, phải dùng đúng tên branch của bạn

Nếu thấy thông báo như sau là đã thành công::

  ...
  Counting objects: 2, done.
  Delta compression using up to 8 threads.
  Compressing objects: 100% (2/2), done.
  Writing objects: 100% (2/2), 234 bytes | 0 bytes/s, done.
  Total 2 (delta 1), reused 0 (delta 0)
  remote:
  remote: To create a merge request for hvn_123, visit:
  remote:   https://gitlab.com/pyfml/pyfml/merge_requests/new?merge_request%5Bsource_branch%5D=hvn_123
  remote:
  To git@gitlab.com:pyfml/pyfml.git
   * [new branch]      hvn_123 -> hvn_123

Tiếp tục làm các bài tập khác, rồi add, commit, push.

**Chú ý: mọi thay đổi trên code đều thực hiện trên máy rồi push lên GitLab,
không chỉnh sửa online trên GitLab**

Mở đường dẫn ở trên để tạo Merge Request (MR) (hoặc làm theo hướng dẫn ở `đây <https://docs.gitlab.com/ee/gitlab-basics/add-merge-request.html>`_).
Trong phần ``Description``, @nick_người_khác để báo cho họ. Cụ thể, mọi MR phải
@hvn_familug và trợ giảng/ giảng viên của khoá.

Bấm vào ``Assignee``, chọn người sẽ review code chính cho bạn, VD trợ giảng của
khoá hoặc người cùng nhóm (sau khi đã phân nhóm).

Bấm vào ``Labels``, chọn khoá mình đang học.

.. image:: mr.png

Bấm ``Submit merge request`` để tạo MR.

Sau khi bấm xong, MR của bạn đã được tạo. Chờ khoảng 5 phút để hệ thống kiểm
tra tự động (CI) kiểm tra bài tập của bạn. Nếu thấy nút X đỏ, với nội dung:

.. image:: pipeline.png

``Pipeline #ABCDEFGH failed``, tức bài tập của bạn không đạt tiêu chuẩn. Bấm vào
``#ABCDEFGH`` để xem chi tiết lỗi. Sau khi bấm vào đó, sẽ thấy một nút X đỏ cạnh
chữ ``test``, bấm tiếp vào để xem chi tiết lỗi.

Tại đây, sẽ thấy các lỗi trong code của bạn dưới dạng::

   ./4_3.py:7:80: E501 line too long (82 > 79 characters)

Tức trong file ``4_3.py``, dòng thứ 7, ký tự 80 gặp lỗi "line too long" - dòng
quá dài so với quy định cho phép tối đa là 79 ký tự.

Sửa lại file lỗi, rồi lại ``git add``, ``git commit``, ``git push``, mọi thay
đổi sẽ được đưa lên GitLab và update Merge Request.


Test riêng một bài
-------------------

Từ thư mục ``pyfml``, chạy::

  $ python -m unittest tests.test_ex3.TestExercise4.test_ex4_9
  E
  ======================================================================
  ERROR: test_ex4_9 (tests.test_ex3.TestExercise4)
  ----------------------------------------------------------------------
  Traceback (most recent call last):
    File "/home/hvn/me/pyfml/tests/test_ex3.py", line 207, in test_ex4_9
      self._test_all(ex4_9.solve, cases)
    File "/home/hvn/me/pyfml/tests/base.py", line 9, in _test_all
      output = func(input)
    File "/home/hvn/me/pyfml/exercises/ex4_9.py", line 12, in solve
      raise NotImplementedError("Học viên chưa làm bài này")
  NotImplementedError: Học viên chưa làm bài này

  ----------------------------------------------------------------------
  Ran 1 test in 0.000s


Debug 1 chương trình
--------------------

Thay vì chạy file python bình thường với câu lệnh::

  python filename.py

Chạy bằng câu lệnh sau để vào chế độ "debug"::

  python -m pdb filename.py

Ở đây:

- bấm ``n`` để chạy sang dòng tiếp theo (n = next)
- bấm ``l`` để hiện xem code đang ở đâu (l = list)
- gõ ``p NAME`` để in ra nội dung của tên ``NAME`` (p = print).
- gõ ``exit`` để thoát.

Ví dụ::

  $ python -m pdb foo.py
  > /home/hvn/foo.py(2)<module>()
  -> s = {"tao": 20,
  (Pdb) n
  > /home/hvn/foo.py(3)<module>()
  -> "Duy": 30,
  (Pdb) l
    1
    2  	s = {"tao": 20,
    3  ->	        "Duy": 30,
    4  	        }
    5
    6  	import logging
    7
    8  	logging.basicConfig(level=logging.DEBUG, filename='my.log')
    9  	logger = logging.getLogger('foo')
   10  	sum_  = 0
   11  	for i in ["tao", "Duy"]:
  (Pdb) n
  > /home/hvn/foo.py(6)<module>()
  -> import logging
  (Pdb) p s
  {'tao': 20, 'Duy': 30}
  (Pdb) exit


Tham khảo các lỗi hay gặp
-------------------------

:doc:`best_practices`


.. toctree::
   :caption: All Exercises Content
   :maxdepth: 2
   :glob:

   exercises/*

Bài tập làm thêm
-----------------

- ProjectEuler https://projecteuler.net/
- HackerRank https://www.hackerrank.com/domains/python/py-introduction
