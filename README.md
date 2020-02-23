# paste
  if (epoch+1)>10 and total_test_loss<mintestloss:        #整体最优
        # if (epoch+1)>10 and Classtest_loss<minClasstestloss:        #类别最优
        # if (epoch+1)>10 and CONCtest_loss<minCONCtestloss:        #浓度最优

            mintestloss=total_test_loss
            # minClasstestloss=Classtest_loss
            # minCONCtestloss=CONCtest_loss

            f = open('Concbestrecord.csv', "w", newline='')
            results_writer(f, all_class_pres, all_class_trues, \
                           test_pre_and_true_concentration[0], test_pre_and_true_concentration[1])



            print("record was updated!The new epokh is %d,The new alltestloss is %.3f"%(epoch+1,total_test_loss))
            # print("record was updated!The new epokh is %d,The new Classtest_loss is %.3f" % (epoch + 1, Classtest_loss))
            # print("record was updated!The new epokh is %d,The new CONCtest_loss is %.3f" % (epoch + 1, CONCtest_loss))
            f.close()
