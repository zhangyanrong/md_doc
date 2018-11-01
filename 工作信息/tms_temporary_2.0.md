一、数据库操作
ALTER TABLE `music`.`teacher_late_punish` 
ADD COLUMN `punish_type` tinyint(2) NOT NULL DEFAULT 1 COMMENT '惩罚类型 1.迟到 2.早退' AFTER `status`,
DROP INDEX `class_id_index`,
ADD UNIQUE INDEX `uniq_class_id_punish_type`(`class_id`, `punish_type`) USING BTREE;

SQL示例:
SELECT `c`.`id`, `c`.`id` AS `class_id`, `c`.`teacher_id`, `t`.`nick` AS `teacher_nick`, `t`.`work_type`, `t`.`work_id`, `c`.`student_id`, `c`.`time_class`, `c`.`time_end`, `c`.`is_ex_class`, `t`.`teacher_master`, `c`.`teacher_in_time` FROM `class_room` `c` inner join `teacher_late_punish` `p` ON `c`.`id` = `p`.`class_id` inner join `user_teacher` `t` ON c.teacher_id = t.id WHERE c.is_deleted=0 AND p.time_class>1538928000 and p.time_class<1539619200 and p.teacher_in_time>0 and c.status in (0,1) and t.is_disabled != 1 AND t.type != 3 AND t.teacher_master in (2,3,4,6,11,14,24,37,49,195,201,666,685,707,877,919,929,937,942,951,953,959,1133,1193,1195,1255,1273,1305,1699,1827,1879,1989,9019,9025,9049,9051,9065,9069,9073,9075,9077,9079,9083,9085,9091,9093,9115,9131,9135,9157,9211,9235,9245,9247,9249,9257,9305,9307,9319,9343,9375,9401,9409,9416,9421,9422,9425,9466,9480,9482,9522,9551,9554,9555,9563,9573,9580,0,9522) and c.time_end<=1539687611 GROUP BY `class_id` ORDER BY `c`.`time_class` LIMIT 8


SELECT `p`.`class_id`, `p`.`status`, `p`.`manager_operate_time`, `p`.`master_operate_time`, `p`.`punish_type`, `p`.`teacher_in_time` AS `in_time`, `p`.`teacher_out_time` AS `out_time`, `p`.`class_length` FROM `teacher_late_punish` `p` WHERE ((p.status>2) AND (p.punish_type=2)) AND (`class_id` IN ('24633384', '24633506', '24633512', '24633589', '24633650', '24633670', '24633675', '24633688'))

SELECT id,class_id,teacher_id,status,time_class,teacher_in_time FROM teacher_late_punish WHERE class_id = 1 AND punish_type = 1

SELECT c.id, time_class, time_end, c.marks, c.teacher_id, teacher_in_time, is_ex_class, course_info, c.status, c.student_id, c.instrument_id, u.nick FROM class_room as c LEFT JOIN user as u ON c.student_id = u.id WHERE c.id = 1

UPDATE teacher_late_punish SET status = 1, operator_master = 1, money = 5, master_operate_time = 1539846755,time_created = 1539846755  WHERE class_id = 1 AND punish_type=1

UPDATE teacher_late_punish SET status = 1, operator_manager = 1, money = 5, manager_operate_time = 1539846755,time_created = 1539846755  WHERE class_id = 1 AND punish_type=1

二、代码上线

APITeacher:tms_6.3

三、临时脚本


四、新建/重启队列


五、定时脚本